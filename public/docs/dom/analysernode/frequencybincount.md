# AnalyserNode.frequencyBinCount

The `frequencyBinCount` read-only property of the [`AnalyserNode`](../analysernode) interface is an unsigned integer half that of the [`AnalyserNode.fftSize`](fftsize). This generally equates to the number of data values you will have to play with for the visualization.

## Syntax

    var arrayLength = analyserNode.frequencyBinCount;

### Value

An unsigned integer, equal to the number of values that [`AnalyserNode.getByteFrequencyData()`](getbytefrequencydata) and [`AnalyserNode.getFloatFrequencyData()`](getfloatfrequencydata) copy into the provided `TypedArray`.

For technical reasons related to how the [Fast Fourier transform](https://en.wikipedia.org/wiki/Fast_Fourier_transform) is defined, it is always half the value of [`AnalyserNode.fftSize`](fftsize). Therefore, it will be one of `16`, `32`, `64`, `128`, `256`, `512`, `1024`, `2048`, `4096`, `8192`, and `16384`.

## Example

The following example shows basic usage of an [`AudioContext`](../audiocontext) to create an `AnalyserNode`, then [`requestAnimationFrame`](../window/requestanimationframe) and [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) to collect frequency data repeatedly and draw a "winamp bargraph style" output of the current audio input. For more complete applied examples/information, check out our [Voice-change-O-matic](https://mdn.github.io/voice-change-o-matic/) demo (see [app.js lines 128–205](https://github.com/mdn/voice-change-o-matic/blob/gh-pages/scripts/app.js#L128-L205) for relevant code).

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var analyser = audioCtx.createAnalyser();
    analyser.minDecibels = -90;
    analyser.maxDecibels = -10;

      ...

    analyser.fftSize = 256;
    var bufferLength = analyser.frequencyBinCount;
    console.log(bufferLength);
    var dataArray = new Uint8Array(bufferLength);

    canvasCtx.clearRect(0, 0, WIDTH, HEIGHT);

    function draw() {
      drawVisual = requestAnimationFrame(draw);

      analyser.getByteFrequencyData(dataArray);

      canvasCtx.fillStyle = 'rgb(0, 0, 0)';
      canvasCtx.fillRect(0, 0, WIDTH, HEIGHT);

      var barWidth = (WIDTH / bufferLength) * 2.5 - 1;
      var barHeight;
      var x = 0;

      for(var i = 0; i < bufferLength; i++) {
        barHeight = dataArray[i];

        canvasCtx.fillStyle = 'rgb(' + (barHeight+100) + ',50,50)';
        canvasCtx.fillRect(x,HEIGHT-barHeight/2,barWidth,barHeight/2);

        x += barWidth;
      }
    };

    draw();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-analysernode-frequencybincount">Web Audio API<br />
<span class="small">The definition of 'frequencyBinCount' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`frequencyBinCount`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/frequencyBinCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/frequencyBinCount</a>
