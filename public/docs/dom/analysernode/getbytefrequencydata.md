# AnalyserNode.getByteFrequencyData()

The `getByteFrequencyData()` method of the [`AnalyserNode`](../analysernode) interface copies the current frequency data into a [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) (unsigned byte array) passed into it.

The frequency data is composed of integers on a scale from 0 to 255.

Each item in the array represents the decibel value for a specific frequency. The frequencies are spread linearly from 0 to 1/2 of the sample rate. For example, for `48000` sample rate, the last item of the array will represent the decibel value for `24000` Hz.

If the array has fewer elements than the [`AnalyserNode.frequencyBinCount`](frequencybincount), excess elements are dropped. If it has more elements than needed, excess elements are ignored.

## Syntax

    var audioCtx = new AudioContext();
    var analyser = audioCtx.createAnalyser();
    var dataArray = new Uint8Array(analyser.frequencyBinCount); // Uint8Array should be the same length as the frequencyBinCount

    void analyser.getByteFrequencyData(dataArray); // fill the Uint8Array with data returned from getByteFrequencyData()

### Parameters

`array`  
The [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) that the frequency domain data will be copied to. For any sample which is silent, the value is `-Infinity`.  
If the array has fewer elements than the [`AnalyserNode.frequencyBinCount`](frequencybincount), excess elements are dropped. If it has more elements than needed, excess elements are ignored.

### Return value

None.

## Example

The following example shows basic usage of an [`AudioContext`](../audiocontext) to create an `AnalyserNode`, then [`requestAnimationFrame`](../window/requestanimationframe) and [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) to collect frequency data repeatedly and draw a "winamp bargraph style" output of the current audio input. For more examples/information, check out our [Voice-change-O-matic](https://mdn.github.io/voice-change-o-matic/) demo (see [app.js lines 128–205](https://github.com/mdn/voice-change-o-matic/blob/gh-pages/scripts/app.js#L128-L205) for relevant code).

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var analyser = audioCtx.createAnalyser();

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

## Parameters

array  
The [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) that the frequency domain data will be copied to.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-analysernode-getbytefrequencydata">Web Audio API<br />
<span class="small">The definition of 'getByteFrequencyData()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`getByteFrequencyData`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/getByteFrequencyData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/getByteFrequencyData</a>
