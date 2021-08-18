# AnalyserNode.smoothingTimeConstant

The `smoothingTimeConstant` property of the [`AnalyserNode`](../analysernode) interface is a double value representing the averaging constant with the last analysis frame. It's basically an average between the current buffer and the last buffer the `AnalyserNode` processed, and results in a much smoother set of value changes over time.

## Syntax

    var smoothValue = analyserNode.smoothingTimeConstant;
    analyserNode.smoothingTimeConstant = newValue;

### Value

A double within the range `0` to `1` (`0` meaning no time averaging). The default value is `0.8`.

If 0 is set, there is no averaging done, whereas a value of 1 means "overlap the previous and current buffer quite a lot while computing the value", which essentially smooths the changes across [`AnalyserNode.getFloatFrequencyData`](getfloatfrequencydata)/[`AnalyserNode.getByteFrequencyData`](getbytefrequencydata) calls.

In technical terms, we apply a [Blackman window](https://webaudio.github.io/web-audio-api/#blackman-window) and smooth the values over time. The default value is good enough for most cases.

**Note**: If a value outside the range 0–1 is set, an `INDEX_SIZE_ERR` exception is thrown.

## Example

The following example shows basic usage of an [`AudioContext`](../audiocontext) to create an `AnalyserNode`, then [`requestAnimationFrame`](../window/requestanimationframe) and [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) to collect frequency data repeatedly and draw a "winamp bargraph style" output of the current audio input. For more complete applied examples/information, check out our [Voice-change-O-matic](https://mdn.github.io/voice-change-o-matic/) demo (see [app.js lines 128–205](https://github.com/mdn/voice-change-o-matic/blob/gh-pages/scripts/app.js#L128-L205) for relevant code).

If you are curious about the effect the `smoothingTimeConstant()` has, try cloning the above example and setting `analyser.smoothingTimeConstant = 0;` instead. You'll notice that the value changes are much more jarring.

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var analyser = audioCtx.createAnalyser();
    analyser.minDecibels = -90;
    analyser.maxDecibels = -10;
    analyser.smoothingTimeConstant = 0.85;

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

      var barWidth = (WIDTH / bufferLength) * 2.5;
      var barHeight;
      var x = 0;

      for(var i = 0; i < bufferLength; i++) {
        barHeight = dataArray[i];

        canvasCtx.fillStyle = 'rgb(' + (barHeight+100) + ',50,50)';
        canvasCtx.fillRect(x,HEIGHT-barHeight/2,barWidth,barHeight/2);

        x += barWidth + 1;
      }
    };

    draw();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-analysernode-smoothingtimeconstant">Web Audio API<br />
<span class="small">The definition of 'smoothingTimeConstant' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`smoothingTimeConstant`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/smoothingTimeConstant" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/smoothingTimeConstant</a>
