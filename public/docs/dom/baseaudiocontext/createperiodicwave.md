# BaseAudioContext.createPeriodicWave()

The `createPeriodicWave()` method of the [`BaseAudioContext`](../baseaudiocontext) Interface is used to create a [`PeriodicWave`](../periodicwave), which is used to define a periodic waveform that can be used to shape the output of an [`OscillatorNode`](../oscillatornode).

## Syntax

    var wave = AudioContext.createPeriodicWave(real, imag[, constraints]);

### Returns

A [`PeriodicWave`](../periodicwave).

### Parameters

`real`  
An array of cosine terms (traditionally the A terms).

`imag`  
An array of sine terms (traditionally the B terms).

The `real` and `imag` arrays have to have the same length, otherwise an error is thrown.

`constraints` <span class="badge inline optional">Optional</span>  
An dictionary object that specifies whether normalization should be disabled (if not specified, normalization is enabled by default.) It takes one property:

- `disableNormalization`: If set to `true`, normalization is disabled for the periodic wave. The default is `false`.

If normalized, the resulting wave will have a maximum absolute peak value of 1.

## Example

The following example illustrates simple usage of `createPeriodicWave()`, to create a [`PeriodicWave`](../periodicwave) object containing a simple sine wave.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-createperiodicwave">Web Audio API<br />
<span class="small">The definition of 'createPeriodicWave' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`createPeriodicWave`

59

Default values supported

30

12

25

No

17

8

59

Default values supported

≤37

59

Default values supported

30

25

18

8

7.0

Default values supported

2.0

`disableNormalisation_supported`

Yes

≤18

No

No

?

No

Yes

Yes

No

?

No

Yes

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createPeriodicWave" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/createPeriodicWave</a>
