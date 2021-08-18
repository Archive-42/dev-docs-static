# OscillatorNode.setPeriodicWave()

The `setPeriodicWave()` method of the [`OscillatorNode`](../oscillatornode) interface is used to point to a [`PeriodicWave`](../periodicwave) defining a periodic waveform that can be used to shape the oscillator's output, when [`type`](type) is `custom`.

## Syntax

    OscillatorNode.setPeriodicWave(wave);

### Parameters

`wave`  
A [`PeriodicWave`](../periodicwave) object representing the waveform to use as the shape of the oscillator's output.

### Returns

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

## Example

The following example illustrates simple usage of `createPeriodicWave()`, recreating a sine wave from a periodic wave.

    var real = new Float32Array(2);
    var imag = new Float32Array(2);
    var ac = new AudioContext();
    var osc = ac.createOscillator();

    real[0] = 0;
    imag[0] = 0;
    real[1] = 1;
    imag[1] = 0;

    var wave = ac.createPeriodicWave(real, imag);

    osc.setPeriodicWave(wave);

    osc.connect(ac.destination);

    osc.start();
    osc.stop(2);

This works because a sound that contains only a fundamental tone is by definition a sine wave.

Here, we create a [`PeriodicWave`](../periodicwave) with two values. The first value is the DC offset, which is the value at which the oscillator starts. 0 is good here, because we want to start the curve at the middle of the \[-1.0; 1.0\] range.

The second and subsequent values are sine and cosine components. You can think of it as the result of a Fourier transform, where you get frequency domain values from time domain value. Here, with `createPeriodicWave()`, you specify the frequencies, and the browser performs a an inverse Fourier transform to get a time domain buffer for the frequency of the oscillator. Here, we only set one component at full volume (1.0) on the fundamental tone, so we get a sine wave.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-oscillatornode-setperiodicwave">Web Audio API<br />
<span class="small">The definition of 'setPeriodicWave' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`setPeriodicWave`

30

12

25

No

17

8

≤37

30

25

18

8

2.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)
- [AudioContext.createPeriodicWave](../baseaudiocontext/createperiodicwave)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode/setPeriodicWave" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OscillatorNode/setPeriodicWave</a>
