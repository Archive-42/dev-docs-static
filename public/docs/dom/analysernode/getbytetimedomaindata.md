# AnalyserNode.getByteTimeDomainData()

The `getByteTimeDomainData()` method of the [`AnalyserNode`](../analysernode) Interface copies the current waveform, or time-domain, data into a [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) (unsigned byte array) passed into it.

If the array has fewer elements than the [`AnalyserNode.fftSize`](fftsize), excess elements are dropped. If it has more elements than needed, excess elements are ignored.

## Syntax

    const audioCtx = new AudioContext();
    const analyser = audioCtx.createAnalyser();
    const dataArray = new Uint8Array(analyser.fftSize); // Uint8Array should be the same length as the fftSize
    analyser.getByteTimeDomainData(dataArray); // fill the Uint8Array with data returned from getByteTimeDomainData()

### Parameters

`array`  
The [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array) that the time domain data will be copied to.  
If the array has fewer elements than the [`AnalyserNode.fftSize`](fftsize), excess elements are dropped. If it has more elements than needed, excess elements are ignored.

### Return value

`void` | None

## Example

The following example shows basic usage of an [`AudioContext`](../audiocontext) to create an `AnalyserNode`, then [`requestAnimationFrame`](../window/requestanimationframe) and [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) to collect time domain data repeatedly and draw an "oscilloscope style" output of the current audio input. For more complete applied examples/information, check out our [Voice-change-O-matic](https://mdn.github.io/voice-change-o-matic/) demo (see [app.js lines 128–205](https://github.com/mdn/voice-change-o-matic/blob/gh-pages/scripts/app.js#L128-L205) for relevant code).

    const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    const analyser = audioCtx.createAnalyser();

      ...

    analyser.fftSize = 2048;
    const bufferLength = analyser.fftSize;
    const dataArray = new Uint8Array(bufferLength);
    analyser.getByteTimeDomainData(dataArray);

    // draw an oscilloscope of the current audio source
    function draw() {
      drawVisual = requestAnimationFrame(draw);
      analyser.getByteTimeDomainData(dataArray);

      canvasCtx.fillStyle = 'rgb(200, 200, 200)';
      canvasCtx.fillRect(0, 0, WIDTH, HEIGHT);

      canvasCtx.lineWidth = 2;
      canvasCtx.strokeStyle = 'rgb(0, 0, 0)';

      const sliceWidth = WIDTH * 1.0 / bufferLength;
      let x = 0;

      canvasCtx.beginPath();
      for(var i = 0; i < bufferLength; i++) {
        const v = dataArray[i]/128.0;
        const y = v * HEIGHT/2;

        if(i === 0)
          canvasCtx.moveTo(x, y);
        else
          canvasCtx.lineTo(x, y);

        x += sliceWidth;
      }

      canvasCtx.lineTo(WIDTH, HEIGHT/2);
      canvasCtx.stroke();
    };

    draw();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-analysernode-getbytetimedomaindata">Web Audio API<br />
<span class="small">The definition of 'getByteTimeDomainData()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`getByteTimeDomainData`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/getByteTimeDomainData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/getByteTimeDomainData</a>
