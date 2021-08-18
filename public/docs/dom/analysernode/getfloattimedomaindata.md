# AnalyserNode.getFloatTimeDomainData()

The `getFloatTimeDomainData()` method of the [`AnalyserNode`](../analysernode) Interface copies the current waveform, or time-domain, data into a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) array passed into it.

## Syntax

    var audioCtx = new AudioContext();
    var analyser = audioCtx.createAnalyser();
    var dataArray = new Float32Array(analyser.fftSize); // Float32Array needs to be the same length as the fftSize
    analyser.getFloatTimeDomainData(dataArray); // fill the Float32Array with data returned from getFloatTimeDomainData()

### Parameters

`array`  
The [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) that the time domain data will be copied to.  
If the array has fewer elements than the [`AnalyserNode.frequencyBinCount`](frequencybincount), excess elements are dropped. If it has more elements than needed, excess elements are ignored.

### Return value

None.

## Example

The following example shows basic usage of an [`AudioContext`](../audiocontext) to create an `AnalyserNode`, then [`requestAnimationFrame`](../window/requestanimationframe) and [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) to collect time domain data repeatedly and draw an "oscilloscope style" output of the current audio input. For more complete applied examples/information, check out our [Voice-change-O-matic-float-data](https://mdn.github.io/voice-change-o-matic-float-data/) demo (see the [source code](https://github.com/mdn/voice-change-o-matic-float-data) too).

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    var analyser = audioCtx.createAnalyser();

      ...

    analyser.fftSize = 1024;
    var bufferLength = analyser.fftSize;
    console.log(bufferLength);
    var dataArray = new Float32Array(bufferLength);

    canvasCtx.clearRect(0, 0, WIDTH, HEIGHT);

    function draw() {
      drawVisual = requestAnimationFrame(draw);
      analyser.getFloatTimeDomainData(dataArray);

      canvasCtx.fillStyle = 'rgb(200, 200, 200)';
      canvasCtx.fillRect(0, 0, WIDTH, HEIGHT);
      canvasCtx.lineWidth = 2;
      canvasCtx.strokeStyle = 'rgb(0, 0, 0)';
      canvasCtx.beginPath();

      var sliceWidth = WIDTH * 1.0 / bufferLength;
      var x = 0;

      for(var i = 0; i < bufferLength; i++) {
        var v = dataArray[i] * 200.0;
        var y = HEIGHT/2 + v;

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

## Parameters

array  
The [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) that the time domain data will be copied to.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-analysernode-getfloattimedomaindata">Web Audio API<br />
<span class="small">The definition of 'getFloatTimeDomainData()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`getFloatTimeDomainData`

14

12

25

No

15

14.1

≤37

18

25

14

14.5

1.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/getFloatTimeDomainData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/getFloatTimeDomainData</a>
