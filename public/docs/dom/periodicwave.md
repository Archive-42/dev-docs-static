# PeriodicWave

The `PeriodicWave` interface defines a periodic waveform that can be used to shape the output of an [`OscillatorNode`](oscillatornode).

`PeriodicWave` has no inputs or outputs; it is used to define custom oscillators when calling [`OscillatorNode.setPeriodicWave()`](oscillatornode/setperiodicwave). The `PeriodicWave` itself is created/returned by [`BaseAudioContext.createPeriodicWave`](baseaudiocontext/createperiodicwave).

## Constructor

[`PeriodicWave.PeriodicWave()`](periodicwave/periodicwave)  
Creates a new `PeriodicWave` object instance using the default values for all properties. If you wish to establish custom property values at the outset, use the [`BaseAudioContext.createPeriodicWave`](baseaudiocontext/createperiodicwave) factory method instead.

## Properties

_None; also, `PeriodicWave` doesn't inherit any properties._

## Methods

_None; also, `PeriodicWave` doesn't inherit any methods._

## Example

The following example illustrates simple usage of `createPeriodicWave()`, to create a [`PeriodicWave`](periodicwave) object containing a simple sine wave.

    var real = new Float32Array(2);
    var imag = new Float32Array(2);
    var ac = new AudioContext();
    var osc = ac.createOscillator();

    real[0] = 0;
    imag[0] = 0;
    real[1] = 1;
    imag[1] = 0;

    var wave = ac.createPeriodicWave(real, imag, {disableNormalization: true});

    osc.setPeriodicWave(wave);

    osc.connect(ac.destination);

    osc.start();
    osc.stop(2);

This works because a sound that contains only a fundamental tone is by definition a sine wave

Here, we create a `PeriodicWave` with two values. The first value is the DC offset, which is the value at which the oscillator starts. 0 is good here, because we want to start the curve at the middle of the \[-1.0; 1.0\] range.

The second and subsequent values are sine and cosine components. You can think of it as the result of a Fourier transform, where you get frequency domain values from time domain value. Here, with `createPeriodicWave()`, you specify the frequencies, and the browser performs an inverse Fourier transform to get a time domain buffer for the frequency of the oscillator. Here, we only set one component at full volume (1.0) on the fundamental tone, so we get a sine wave.

The coefficients of the Fourier transform should be given in _ascending_ order (i.e. (_a_+_b\*\*i_)_e_<sup>_i_</sup>, (_c_+_d\*\*i_)_e_<sup>2*i*</sup>, (_f_+_g\*\*i_)_e_<sup>3*i*</sup>etc.) and can be positive or negative. A simple way of manually obtaining such coefficients (though not the best) is to use a graphing calculator.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#periodicwave">Web Audio API<br />
<span class="small">The definition of 'PeriodicWave' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`PeriodicWave`

30

≤18

25

No

17

8

≤37

30

26

18

8

2.0

`PeriodicWave`

55

Before Chrome 59, the default values were not supported.

≤79

53

No

42

14.1

55

Before Chrome 59, the default values were not supported.

55

Before Chrome 59, the default values were not supported.

53

42

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

## See also

- [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PeriodicWave" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PeriodicWave</a>
