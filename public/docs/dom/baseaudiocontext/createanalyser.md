# BaseAudioContext.createAnalyser()

The `createAnalyser()` method of the [`BaseAudioContext`](../baseaudiocontext) interface creates an [`AnalyserNode`](../analysernode), which can be used to expose audio time and frequency data and create data visualisations.

**Note**: For more on using this node, see the [`AnalyserNode`](../analysernode) page.

## Syntax

    var analyserNode = baseAudioContext.createAnalyser();

### Returns

An [`AnalyserNode`](../analysernode).

## Example

The following example shows basic usage of an AudioContext to create an Analyser node, then use requestAnimationFrame() to collect time domain data repeatedly and draw an "oscilloscope style" output of the current audio input. For more complete applied examples/information, check out our [Voice-change-O-matic](https://mdn.github.io/voice-change-o-matic/) demo (see [app.js lines 128–205](https://github.com/mdn/voice-change-o-matic/blob/gh-pages/scripts/app.js#L128-L205) for relevant code).

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var analyser = audioCtx.createAnalyser();

      ...

    analyser.fftSize = 2048;
    var bufferLength = analyser.frequencyBinCount;
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-createanalyser">Web Audio API<br />
<span class="small">The definition of 'createAnalyser()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`createAnalyser`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createAnalyser" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createAnalyser</a>
