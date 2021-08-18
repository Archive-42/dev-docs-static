Visualizations with Web Audio API
=================================

One of the most interesting features of the Web Audio API is the ability to extract frequency, waveform, and other data from your audio source, which can then be used to create visualizations. This article explains how, and provides a couple of basic use cases.

**Note**: You can find working examples of all the code snippets in our [Voice-change-O-matic](https://mdn.github.io/voice-change-o-matic/) demo.

Basic concepts
--------------

To extract data from your audio source, you need an [`AnalyserNode`](../analysernode), which is created using the [`BaseAudioContext.createAnalyser`](../baseaudiocontext/createanalyser) method, for example:

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var analyser = audioCtx.createAnalyser();

This node is then connected to your audio source at some point between your source and your destination, for example:

    source = audioCtx.createMediaStreamSource(stream);
    source.connect(analyser);
    analyser.connect(distortion);
    distortion.connect(audioCtx.destination);

**Note**: you don't need to connect the analyser's output to another node for it to work, as long as the input is connected to the source, either directly or via another node.

The analyser node will then capture audio data using a Fast Fourier Transform (fft) in a certain frequency domain, depending on what you specify as the [`AnalyserNode.fftSize`](../analysernode/fftsize) property value (if no value is specified, the default is 2048.)

**Note**: You can also specify a minimum and maximum power value for the fft data scaling range, using [`AnalyserNode.minDecibels`](../analysernode/mindecibels) and [`AnalyserNode.maxDecibels`](../analysernode/maxdecibels), and different data averaging constants using [`AnalyserNode.smoothingTimeConstant`](../analysernode/smoothingtimeconstant). Read those pages to get more information on how to use them.

To capture data, you need to use the methods [`AnalyserNode.getFloatFrequencyData()`](../analysernode/getfloatfrequencydata) and [`AnalyserNode.getByteFrequencyData()`](../analysernode/getbytefrequencydata) to capture frequency data, and [`AnalyserNode.getByteTimeDomainData()`](../analysernode/getbytetimedomaindata) and [`AnalyserNode.getFloatTimeDomainData()`](../analysernode/getfloattimedomaindata) to capture waveform data.

These methods copy data into a specified array, so you need to create a new array to receive the data before invoking one. The first one produces 32-bit floating point numbers, and the second and third ones produce 8-bit unsigned integers, therefore a standard JavaScript array won't do — you need to use a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) or [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) array, depending on what data you are handling.

So for example, say we are dealing with an fft size of 2048. We return the [`AnalyserNode.frequencyBinCount`](../analysernode/frequencybincount) value, which is half the fft, then call Uint8Array() with the frequencyBinCount as its length argument — this is how many data points we will be collecting, for that fft size.

    analyser.fftSize = 2048;
    var bufferLength = analyser.frequencyBinCount;
    var dataArray = new Uint8Array(bufferLength);

To actually retrieve the data and copy it into our array, we then call the data collection method we want, with the array passed as it's argument. For example:

    analyser.getByteTimeDomainData(dataArray);

We now have the audio data for that moment in time captured in our array, and can proceed to visualize it however we like, for example by plotting it onto an HTML5 [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas).

Let's go on to look at some specific examples.

Creating a waveform/oscilloscope
--------------------------------

To create the oscilloscope visualisation (hat tip to [Soledad Penadés](https://soledadpenades.com/) for the original code in [Voice-change-O-matic](https://github.com/mdn/voice-change-o-matic/blob/gh-pages/scripts/app.js#L123-L167)), we first follow the standard pattern described in the previous section to set up the buffer:

    analyser.fftSize = 2048;
    var bufferLength = analyser.frequencyBinCount;
    var dataArray = new Uint8Array(bufferLength);

Next, we clear the canvas of what had been drawn on it before to get ready for the new visualization display:

    canvasCtx.clearRect(0, 0, WIDTH, HEIGHT);

We now define the `draw()` function:

    function draw() {

In here, we use `requestAnimationFrame()` to keep looping the drawing function once it has been started:

    var drawVisual = requestAnimationFrame(draw);

Next, we grab the time domain data and copy it into our array

    analyser.getByteTimeDomainData(dataArray);

Next, fill the canvas with a solid color to start

    canvasCtx.fillStyle = 'rgb(200, 200, 200)';
    canvasCtx.fillRect(0, 0, WIDTH, HEIGHT);

Set a line width and stroke color for the wave we will draw, then begin drawing a path

    canvasCtx.lineWidth = 2;
    canvasCtx.strokeStyle = 'rgb(0, 0, 0)';
    canvasCtx.beginPath();

Determine the width of each segment of the line to be drawn by dividing the canvas width by the array length (equal to the FrequencyBinCount, as defined earlier on), then define an x variable to define the position to move to for drawing each segment of the line.

    var sliceWidth = WIDTH * 1.0 / bufferLength;
    var x = 0;

Now we run through a loop, defining the position of a small segment of the wave for each point in the buffer at a certain height based on the data point value form the array, then moving the line across to the place where the next wave segment should be drawn:

          for(var i = 0; i < bufferLength; i++) {

            var v = dataArray[i] / 128.0;
            var y = v * HEIGHT/2;

            if(i === 0) {
              canvasCtx.moveTo(x, y);
            } else {
              canvasCtx.lineTo(x, y);
            }

            x += sliceWidth;
          }

Finally, we finish the line in the middle of the right hand side of the canvas, then draw the stroke we've defined:

          canvasCtx.lineTo(canvas.width, canvas.height/2);
          canvasCtx.stroke();
        };

At the end of this section of code, we invoke the `draw()` function to start off the whole process:

        draw();

This gives us a nice waveform display that updates several times a second:

<img src="data:image/png;base64,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" alt="a black oscilloscope line, showing the waveform of an audio signal" width="640" height="96" />

Creating a frequency bar graph
------------------------------

Another nice little sound visualization to create is one of those Winamp-style frequency bar graphs. We have one available in Voice-change-O-matic; let's look at how it's done.

First, we again set up our analyser and data array, then clear the current canvas display with `clearRect()`. The only difference from before is that we have set the fft size to be much smaller; this is so that each bar in the graph is big enough to actually look like a bar rather than a thin strand.

    analyser.fftSize = 256;
    var bufferLength = analyser.frequencyBinCount;
    console.log(bufferLength);
    var dataArray = new Uint8Array(bufferLength);

    canvasCtx.clearRect(0, 0, WIDTH, HEIGHT);

Next, we start our `draw()` function off, again setting up a loop with `requestAnimationFrame()` so that the displayed data keeps updating, and clearing the display with each animation frame.

        function draw() {
          drawVisual = requestAnimationFrame(draw);

          analyser.getByteFrequencyData(dataArray);

          canvasCtx.fillStyle = 'rgb(0, 0, 0)';
          canvasCtx.fillRect(0, 0, WIDTH, HEIGHT);

Now we set our `barWidth` to be equal to the canvas width divided by the number of bars (the buffer length). However, we are also multiplying that width by 2.5, because most of the frequencies will come back as having no audio in them, as most of the sounds we hear every day are in a certain lower frequency range. We don't want to display loads of empty bars, therefore we shift the ones that will display regularly at a noticeable height across so they fill the canvas display.

We also set a `barHeight` variable, and an `x` variable to record how far across the screen to draw the current bar.

    var barWidth = (WIDTH / bufferLength) * 2.5;
    var barHeight;
    var x = 0;

As before, we now start a for loop and cycle through each value in the `dataArray`. For each one, we make the `barHeight` equal to the array value, set a fill color based on the `barHeight` (taller bars are brighter), and draw a bar at `x` pixels across the canvas, which is `barWidth` wide and `barHeight/2` tall (we eventually decided to cut each bar in half so they would all fit on the canvas better.)

The one value that needs explaining is the vertical offset position we are drawing each bar at: `HEIGHT-barHeight/2`. I am doing this because I want each bar to stick up from the bottom of the canvas, not down from the top, as it would if we set the vertical position to 0. Therefore, we instead set the vertical position each time to the height of the canvas minus `barHeight/2`, so therefore each bar will be drawn from partway down the canvas, down to the bottom.

          for(var i = 0; i < bufferLength; i++) {
            barHeight = dataArray[i]/2;

            canvasCtx.fillStyle = 'rgb(' + (barHeight+100) + ',50,50)';
            canvasCtx.fillRect(x,HEIGHT-barHeight/2,barWidth,barHeight);

            x += barWidth + 1;
          }
        };

Again, at the end of the code we invoke the draw() function to set the whole process in motion.

    draw();

This code gives us a result like the following:

<img src="data:image/png;base64,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" alt="a series of red bars in a bar graph, showing intensity of different frequencies in an audio signal" width="1260" height="157" />

**Note**: The examples listed in this article have shown usage of [`AnalyserNode.getByteFrequencyData()`](../analysernode/getbytefrequencydata) and [`AnalyserNode.getByteTimeDomainData()`](../analysernode/getbytetimedomaindata). For working examples showing [`AnalyserNode.getFloatFrequencyData()`](../analysernode/getfloatfrequencydata) and [`AnalyserNode.getFloatTimeDomainData()`](../analysernode/getfloattimedomaindata), refer to our [Voice-change-O-matic-float-data](https://mdn.github.io/voice-change-o-matic-float-data/) demo (see the [source code](https://github.com/mdn/voice-change-o-matic-float-data) too) — this is exactly the same as the original [Voice-change-O-matic](https://mdn.github.io/voice-change-o-matic/), except that it uses Float data, not unsigned byte data.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Visualizations_with_Web_Audio_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Visualizations_with_Web_Audio_API</a>
