# BiquadFilterNode()

The `BiquadFilterNode()` constructor of the [Web Audio API](../web_audio_api) creates a new [`BiquadFilterNode`](../biquadfilternode) object, which represents a simple low-order filter, and is created using the AudioContext.createBiquadFilter() method.

## Syntax

    var biquadFilterNode = new BiquadFilterNode(context, options)

### Parameters

_Inherits parameters from the [`AudioNodeOptions`](../audionodeoptions) dictionary_.

_context_  
A reference to an [`AudioContext`](../audiocontext).

_options_ <span class="badge inline optional">Optional</span>  
Options are as follows:

- `type`: One of "`lowpass`", "`highpass`", "`bandpass`", "`lowshelf`", "`highshelf`", "`peaking`", "`notch`", "`allpass`". The meaning of the other options depends on the value of this one. The defaults for all are as follows:
  - `Q`: `1`
  - `detune`: `0`
  - `frequency`: `350`
  - `gain`: `0`

`lowpass`: (Default) Allows frequencies below a cutoff frequency to pass through, and attenuates frequencies above the cutoff. This is a standard second-order resonant lowpass filter with 12dB/octave rolloff.

- `Q`: Controls how peaked the response will be at the cutoff frequency. A large value makes the response more peaked. Please note that for this filter type, this value is not a traditional Q, but is a resonance value in decibels.
- `frequency`: The cutoff frequency.
- `gain`: Not used.

`highpass`: A highpass filter is the opposite of a lowpass filter. Frequencies above the cutoff frequency are passed through, but frequencies below the cutoff are attenuated. It implements a standard second-order resonant highpass filter with 12dB/octave rolloff.

- `Q`: Controls how peaked the response will be at the cutoff frequency. A large value makes the response more peaked. Please note that for this filter type, this value is not a traditional Q, but is a resonance value in decibels.
- `frequency`: The cutoff frequency.
- `gain`: Not used.

`bandpass`: A bandpass filter allows a range of frequencies to pass through and attenuates the frequencies below and above this frequency range. It implements a second-order bandpass filter.

- `Q`: Controls the width of the band. The width becomes narrower as the Q value increases.
- `frequency`: The center of the frequency band.
- `gain`: Not used.

`lowshelf`: The lowshelf filter allows all frequencies through, but adds a boost (or attenuation) to the lower frequencies. It implements a second-order lowshelf filter.

- `Q`: Not used.
- `frequency`: The upper limit of the frequencies where the boost, or attenuation, is applied.
- `gain`: The boost, in dB, to be applied. If the value is negative, the frequencies are attenuated.

`highshelf`: The highshelf filter is the opposite of the lowshelf filter and allows all frequencies through, but adds a boost to the higher frequencies. It implements a second-order highshelf filter.

- `Q`: Not used.
- `frequency`: The lower limit of the frequencies where the boost, or attenuation, is applied.
- `gain`: The boost, in dB, to be applied. If the value is negative, the frequencies are attenuated.

`peaking`: The peaking filter allows all frequencies through, adding a boost, or attenuation, to a range of frequencies.

- `Q`: The width of the band of frequencies that are boosted. A large value implies a narrow width.
- `frequency`: The center frequency of the boost range.
- `gain`: The boost, in dB, to be applied. If the value is negative, the frequencies are attenuated.

`notch`: The notch filter (also known as a band-stop, or band-rejection filter) is the opposite of a bandpass filter. It allows all frequencies through, except for a set of frequencies.

- `Q`: The width of the band of frequencies that are attenuated. A large value implies a narrow width.
- `frequency`: The center frequency of the attenuation range.
- `gain`: Not used.

`allpass`: An allpass filter allows all frequencies through, but changes the phase relationship between the various frequencies. It implements a second-order allpass filter.

- `Q`: The sharpness of the phase transition at the center frequency. A larger value implies a sharper transition and a larger group delay.
- `frequency`: The frequency where the center of the phase transition occurs. Viewed another way, this is the frequency with maximal group delay.
- `gain`: Not used.

### Return value

A new [`BiquadFilterNode`](../biquadfilternode) object instance.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-biquadfilternode-biquadfilternode">Web Audio API<br />
<span class="small">The definition of 'BiquadFilterNode()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`BiquadFilterNode`

55

Before Chrome 59, the default values were not supported.

79

53

No

42

Before Opera 46, the default values were not supported.

14.1

55

Before version 59, the default values were not supported.

55

Before Chrome 59, the default values were not supported.

53

42

Before Opera 46, the default values were not supported.

14.5

6.0

Before Samsung Internet 7.0, the default values were not supported.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BiquadFilterNode/BiquadFilterNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BiquadFilterNode/BiquadFilterNode</a>
