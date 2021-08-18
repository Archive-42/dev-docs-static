# BaseAudioContext.createOscillator()

The `createOscillator()` method of the [`BaseAudioContext`](../baseaudiocontext) interface creates an [`OscillatorNode`](../oscillatornode), a source representing a periodic waveform. It basically generates a constant tone.

## Syntax

    var oscillatorNode = audioCtx.createOscillator();

### Returns

An [`OscillatorNode`](../oscillatornode).

## Example

The following example shows basic usage of an AudioContext to create an oscillator node. For applied examples/information, check out our [Violent Theremin demo](https://mdn.github.io/violent-theremin/) ([see app.js](https://github.com/mdn/violent-theremin/blob/gh-pages/scripts/app.js) for relevant code); also see our [`OscillatorNode`](../oscillatornode) page for more information.

    // create web audio api context
    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();

    // create Oscillator node
    var oscillator = audioCtx.createOscillator();

    oscillator.type = 'square';
    oscillator.frequency.setValueAtTime(3000, audioCtx.currentTime); // value in hertz
    oscillator.connect(audioCtx.destination);
    oscillator.start();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-createoscillator">Web Audio API<br />
<span class="small">The definition of 'createOscillator' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`createOscillator`

20

12

25

No

15

6

≤37

25

25

14

6

1.5

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createOscillator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createOscillator</a>
