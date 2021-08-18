# PeriodicWave.PeriodicWave()

The `PeriodicWave()` constructor of the [Web Audio API](../web_audio_api) creates a new [`PeriodicWave`](../periodicwave) object instance.

## Syntax

    var myWave = new PeriodicWave(context, options);

### Parameters

_Inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary_.

`context`  
A [`BaseAudioContext`](../baseaudiocontext) representing the audio context you want the node to be associated with.

`options` <span class="badge inline optional">Optional</span>  
A `PeriodicWaveOptions` dictionary object defining the properties you want the `PeriodicWave` to have (It also inherits the options defined in the [PeriodicWaveConstraints](https://webaudio.github.io/web-audio-api/#idl-def-PeriodicWaveConstraints) dictionary.):

- `real`: A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) containing the cosine terms that you want to use to form the wave (equivalent to the `real` parameter of [`BaseAudioContext.createPeriodicWave`](../baseaudiocontext/createperiodicwave)).
- `imag`: A [`Float32Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Float32Array) containing the sine terms that you want to use to form the wave (equivalent to the `imag` parameter of [`BaseAudioContext.createPeriodicWave`](../baseaudiocontext/createperiodicwave)).

### Return value

A new [`PeriodicWave`](../periodicwave) object instance.

## Example

    var real = new Float32Array(2);
    var imag = new Float32Array(2);
    var ac = new AudioContext();

    real[0] = 0;
    imag[0] = 0;
    real[1] = 1;
    imag[1] = 0;

    var options = {
      real : real,
      imag : imag,
      disableNormalization : false
    }

    var wave = new PeriodicWave(ac, options);

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PeriodicWave/PeriodicWave" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PeriodicWave/PeriodicWave</a>
