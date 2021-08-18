# OscillatorNode.type

The `type` property of the [`OscillatorNode`](../oscillatornode) interface specifies what shape of [waveform](https://en.wikipedia.org/wiki/Waveform) the oscillator will output. There are several common waveforms available, as well as an option to specify a custom waveform shape. The shape of the waveform will affect the tone that is produced.

## Syntax

    OscillatorNode.type = type;

### Value

A [`DOMString`](../domstring) specifying the shape of oscillator wave. The different available values are:

`sine`  
A [sine wave](https://en.wikipedia.org/wiki/Sine_wave). This is the default value.

`square`  
A [square wave](https://en.wikipedia.org/wiki/Square_wave) with a [duty cycle](#) of 0.5; that is, the signal is "high" for half of each period.

`sawtooth`  
A [sawtooth wave](https://en.wikipedia.org/wiki/Sawtooth_wave).

`triangle`  
A [triangle wave](https://en.wikipedia.org/wiki/Triangle_wave).

`custom`  
A custom waveform. You never set `type` to `custom` manually; instead, use the [`setPeriodicWave()`](setperiodicwave) method to provide the data representing the waveform. Doing so automatically sets the `type` to `custom`.

### Exceptions

`InvalidStateError`  
The value `custom` was specified. To set a custom waveform, just call [`setPeriodicWave()`](setperiodicwave). Doing so automatically sets the type for you.

## Example

The following example shows basic usage of an [`AudioContext`](../audiocontext) to create an oscillator node. For an applied example, check out our [Violent Theremin demo](https://mdn.github.io/violent-theremin/) ([see app.js](https://github.com/mdn/violent-theremin/blob/gh-pages/scripts/app.js) for relevant code).

    // create web audio api context
    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();

    // create Oscillator node
    var oscillator = audioCtx.createOscillator();

    oscillator.type = 'square';
    oscillator.frequency.setValueAtTime(440, audioCtx.currentTime); // value in hertz
    oscillator.start();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-oscillatornode-type">Web Audio API<br />
<span class="small">The definition of 'type' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`type`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode/type</a>
