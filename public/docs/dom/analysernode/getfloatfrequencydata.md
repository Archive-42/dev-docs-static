# AnalyserNode.getFloatFrequencyData()

The `getFloatFrequencyData()` method of the [`AnalyserNode`](../analysernode) Interface copies the current frequency data into a [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) array passed into it.

Each item in the array represents the decibel value for a specific frequency. The frequencies are spread linearly from 0 to 1/2 of the sample rate. For example, for a `48000` Hz sample rate, the last item of the array will represent the decibel value for `24000` Hz.

If you need higher performance and don't care about precision, you can use [`AnalyserNode.getByteFrequencyData()`](getbytefrequencydata) instead, which works on a [`Uint8Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8Array).

## Syntax

    var audioCtx = new AudioContext();
    var analyser = audioCtx.createAnalyser();
    var dataArray = new Float32Array(analyser.frequencyBinCount); // Float32Array should be the same length as the frequencyBinCount

    void analyser.getFloatFrequencyData(dataArray); // fill the Float32Array with data returned from getFloatFrequencyData()

### Parameters

`array`  
The [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) that the frequency domain data will be copied to. For any sample which is silent, the value is `-Infinity`.  
If the array has fewer elements than the [`AnalyserNode.frequencyBinCount`](frequencybincount), excess elements are dropped. If it has more elements than needed, excess elements are ignored.

### Return value

None.

## Example

    const audioCtx = new AudioContext();
    const analyser = audioCtx.createAnalyser();
    // Float32Array should be the same length as the frequencyBinCount
    const myDataArray = new Float32Array(analyser.frequencyBinCount);
    // fill the Float32Array with data returned from getFloatFrequencyData()
    analyser.getFloatFrequencyData(myDataArray);

### Drawing a spectrum

The following example shows basic usage of an [`AudioContext`](../audiocontext) to connect a [`MediaElementAudioSourceNode`](../mediaelementaudiosourcenode) to an `AnalyserNode`. While the audio is playing, we collect the frequency data repeatedly with [`requestAnimationFrame()`](../window/requestanimationframe) and draw a "winamp bargraph style" to a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element.

For more complete applied examples/information, check out our [Voice-change-O-matic-float-data](https://mdn.github.io/voice-change-o-matic-float-data/) demo (see the [source code](https://github.com/mdn/voice-change-o-matic-float-data) too).

    <!doctype html>
    <body>
    <script>
    const audioCtx = new AudioContext();

    //Create audio source
    //Here, we use an audio file, but this could also be e.g. microphone input
    const audioEle = new Audio();
    audioEle.src = 'my-audio.mp3';//insert file name here
    audioEle.autoplay = true;
    audioEle.preload = 'auto';
    const audioSourceNode = audioCtx.createMediaElementSource(audioEle);

    //Create analyser node
    const analyserNode = audioCtx.createAnalyser();
    analyserNode.fftSize = 256;
    const bufferLength = analyserNode.frequencyBinCount;
    const dataArray = new Float32Array(bufferLength);

    //Set up audio node network
    audioSourceNode.connect(analyserNode);
    analyserNode.connect(audioCtx.destination);

    //Create 2D canvas
    const canvas = document.createElement('canvas');
    canvas.style.position = 'absolute';
    canvas.style.top = 0;
    canvas.style.left = 0;
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
    document.body.appendChild(canvas);
    const canvasCtx = canvas.getContext('2d');
    canvasCtx.clearRect(0, 0, canvas.width, canvas.height);

    function draw() {
      //Schedule next redraw
      requestAnimationFrame(draw);

      //Get spectrum data
      analyserNode.getFloatFrequencyData(dataArray);

      //Draw black background
      canvasCtx.fillStyle = 'rgb(0, 0, 0)';
      canvasCtx.fillRect(0, 0, canvas.width, canvas.height);

      //Draw spectrum
      const barWidth = (canvas.width / bufferLength) * 2.5;
      let posX = 0;
      for (let i = 0; i < bufferLength; i++) {
        const barHeight = (dataArray[i] + 140) * 2;
        canvasCtx.fillStyle = 'rgb(' + Math.floor(barHeight + 100) + ', 50, 50)';
        canvasCtx.fillRect(posX, canvas.height - barHeight / 2, barWidth, barHeight / 2);
        posX += barWidth + 1;
      }
    };

    draw();
    </script>
    </body>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-analysernode-getfloatfrequencydata">Web Audio API<br />
<span class="small">The definition of 'getFloatFrequencyData()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`getFloatFrequencyData`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/getFloatFrequencyData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnalyserNode/getFloatFrequencyData</a>
