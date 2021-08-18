# AnalyserNode.fftSize

The `fftSize` property of the [`AnalyserNode`](../analysernode) interface is an unsigned long value and represents the window size in samples that is used when performing a [Fast Fourier Transform](https://en.wikipedia.org/wiki/Fast_Fourier_transform) (FFT) to get frequency domain data.

## Syntax

    var curValue = analyserNode.fftSize;
    analyserNode.fftSize = newValue;

### Value

An unsigned integer, representing the window size of the FFT, given in number of samples. A higher value will result in more details in the frequency domain but fewer details in the time domain.

Must be a power of 2 between 2<sup>5</sup> and 2<sup>15</sup>, so one of: `32`, `64`, `128`, `256`, `512`, `1024`, `2048`, `4096`, `8192`, `16384`, and `32768`. Defaults to `2048`.

**Note**: If its value is not a power of 2, or it is outside the specified range, a [`DOMException`](../domexception) with the name `IndexSizeError` is thrown.

## Example

The following example shows basic usage of an [`AudioContext`](../audiocontext) to create an `AnalyserNode`, then [`requestAnimationFrame`](../window/requestanimationframe) and [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) to collect time domain data repeatedly and draw an "oscilloscope style" output of the current audio input. For more complete applied examples/information, check out our [Voice-change-O-matic](https://mdn.github.io/voice-change-o-matic/) demo (see [app.js lines 128–205](https://github.com/mdn/voice-change-o-matic/blob/gh-pages/scripts/app.js#L128-L205) for relevant code).

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var analyser = audioCtx.createAnalyser();

      ...

    analyser.fftSize = 2048;
    var bufferLength = analyser.frequencyBinCount ;
    var dataArray = new Uint8Array(bufferLength);
    analyser.getByteTimeDomainData(dataArray);

    // draw an oscilloscope of the current audio source

    function draw() {

          drawVisual = requestAnimationFrame(draw);

          analyser.getByteTimeDomainData(dataArray);

          canvasCtx.fillStyle = 'rgb(200, 200, 200)';
          canvasCtx.fillRect(0, 0, WIDTH, HEIGHT);

          canvasCtx.lineWidth = 2;
          canvasCtx.strokeStyle = 'rgb(0, 0, 0)';

          canvasCtx.beginPath();

          var sliceWidth = WIDTH * 1.0 / bufferLength;
          var x = 0;

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

          canvasCtx.lineTo(canvas.width, canvas.height/2);
          canvasCtx.stroke();
        };

        draw();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-analysernode-fftsize">Web Audio API<br />
<span class="small">The definition of 'fftSize' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

## Browser compatibility

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`fftSize`

14

12

25

No

15

6

≤37

18

25

14

6

1.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/fftSize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/fftSize</a>
