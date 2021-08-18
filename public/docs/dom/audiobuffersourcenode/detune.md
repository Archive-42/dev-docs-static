# AudioBufferSourceNode.detune

The `detune` property of the [`AudioBufferSourceNode`](../audiobuffersourcenode) interface is a [k-rate](../audioparam#k-rate) [`AudioParam`](../audioparam) representing detuning of oscillation in [cents](https://en.wikipedia.org/wiki/Cent_%28music%29).

For example, values of +100 and -100 detune the source up or down by one semitone, while +1200 and -1200 detune it up or down by one octave.

## Syntax

    var source = audioCtx.createBufferSource();
    source.detune.value = 100; // value in cents

**Note:** Though the `AudioParam` returned is read-only, the value it represents is not.

### Value

A [k-rate](../audioparam#k-rate) [`AudioParam`](../audioparam) whose value indicates the detuning of oscillation in [cents](https://en.wikipedia.org/wiki/Cent_%28music%29).

## Example

    const audioCtx = new AudioContext();

    const channelCount = 2;
    const frameCount = audioCtx.sampleRate * 2.0; // 2 seconds

    const myArrayBuffer = audioCtx.createBuffer(channelCount, frameCount, audioCtx.sampleRate);

    for (let channel = 0; channel < channelCount; channel++) {
      const nowBuffering = myArrayBuffer.getChannelData(channel);
      for (let i = 0; i < frameCount; i++) {
        nowBuffering[i] = Math.random() * 2 - 1;
      }
    }

    const source = audioCtx.createBufferSource();
    source.buffer = myArrayBuffer;
    source.connect(audioCtx.destination);
    source.detune.value = 100; // value in cents
    source.start();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiobuffersourcenode-detune">Web Audio API<br />
<span class="small">The definition of 'detune' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`detune`

44

13

40

No

31

14.1

44

44

40

32

14.5

4.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode/detune" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioBufferSourceNode/detune</a>
