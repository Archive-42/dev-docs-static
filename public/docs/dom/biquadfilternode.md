# BiquadFilterNode

The `BiquadFilterNode` interface represents a simple low-order filter, and is created using the [`BaseAudioContext/createBiquadFilter`](baseaudiocontext/createbiquadfilter) method. It is an [`AudioNode`](audionode) that can represent different kinds of filters, tone control devices, and graphic equalizers. A `BiquadFilterNode` always has exactly one input and one output.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>1</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"max"</code></td></tr><tr class="even"><td>Channel count</td><td><code>2</code> (not used in the default count mode)</td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

## Constructor

[`BiquadFilterNode()`](biquadfilternode/biquadfilternode)  
Creates a new instance of a `BiquadFilterNode` object.

## Properties

_Inherits properties from its parent, [`AudioNode`](audionode)_.

**Note**: Though the `AudioParam` objects returned are read-only, the values they represent are not.

[`BiquadFilterNode.frequency`](biquadfilternode/frequency) <span class="badge inline readonly">Read only </span>  
Is an [a-rate](audioparam#a-rate) [`AudioParam`](audioparam), a double representing a frequency in the current filtering algorithm measured in hertz (Hz).

[`BiquadFilterNode.detune`](biquadfilternode/detune) <span class="badge inline readonly">Read only </span>  
Is an [a-rate](audioparam#a-rate) [`AudioParam`](audioparam) representing detuning of the frequency in [cents](https://en.wikipedia.org/wiki/Cent_%28music%29).

[`BiquadFilterNode.Q`](biquadfilternode/q) <span class="badge inline readonly">Read only </span>  
Is an [a-rate](audioparam#a-rate) [`AudioParam`](audioparam), a double representing a [Q factor](https://en.wikipedia.org/wiki/Q_factor), or _quality factor_.

[`BiquadFilterNode.gain`](biquadfilternode/gain) <span class="badge inline readonly">Read only </span>  
Is an [a-rate](audioparam#a-rate) [`AudioParam`](audioparam), a double representing the [gain](https://en.wikipedia.org/wiki/Gain) used in the current filtering algorithm.

[`BiquadFilterNode.type`](biquadfilternode/type)  
Is a string value defining the kind of filtering algorithm the node is implementing.

<table><caption>The meaning of the different parameters depending of the type of the filter (detune has the same meaning regardless, so isn't listed below)</caption><thead><tr class="header"><th><code>type</code></th><th>Description</th><th><code>frequency</code></th><th><code>Q</code></th><th><code>gain</code></th></tr></thead><tbody><tr class="odd"><td><code>lowpass</code></td><td>Standard second-order resonant lowpass filter with 12dB/octave rolloff. Frequencies below the cutoff pass through; frequencies above it are attenuated.</td><td>The cutoff frequency.</td><td>Indicates how peaked the frequency is around the cutoff. The greater the value is, the greater is the peak.</td><td><em>Not used</em></td></tr><tr class="even"><td><code>highpass</code></td><td>Standard second-order resonant highpass filter with 12dB/octave rolloff. Frequencies below the cutoff are attenuated; frequencies above it pass through.</td><td>The cutoff frequency.</td><td>Indicates how peaked the frequency is around the cutoff. The greater the value, the greater the peak.</td><td><em>Not used</em></td></tr><tr class="odd"><td><code>bandpass</code></td><td>Standard second-order bandpass filter. Frequencies outside the given range of frequencies are attenuated; the frequencies inside it pass through.</td><td>The center of the range of frequencies.</td><td>Controls the width of the frequency band. The greater the <code>Q</code> value, the smaller the frequency band.</td><td><em>Not used</em></td></tr><tr class="even"><td><code>lowshelf</code></td><td>Standard second-order lowshelf filter. Frequencies lower than the frequency get a boost, or an attenuation; frequencies over it are unchanged.</td><td>The upper limit of the frequencies getting a boost or an attenuation.</td><td><em>Not used</em></td><td>The boost, in dB, to be applied; if negative, it will be an attenuation.</td></tr><tr class="odd"><td><code>highshelf</code></td><td>Standard second-order highshelf filter. Frequencies higher than the frequency get a boost or an attenuation; frequencies lower than it are unchanged.</td><td>The lower limit of the frequencies getting a boost or an attenuation.</td><td><em>Not used</em></td><td>The boost, in dB, to be applied; if negative, it will be an attenuation.</td></tr><tr class="even"><td><code>peaking</code></td><td>Frequencies inside the range get a boost or an attenuation; frequencies outside it are unchanged.</td><td>The middle of the frequency range getting a boost or an attenuation.</td><td>Controls the width of the frequency band. The greater the <code>Q</code> value, the smaller the frequency band.</td><td>The boost, in dB, to be applied; if negative, it will be an attenuation.</td></tr><tr class="odd"><td><code>notch</code></td><td>Standard <a href="https://en.wikipedia.org/wiki/Band-stop_filter">notch</a> filter, also called a <em>band-stop</em> or <em>band-rejection</em> filter. It is the opposite of a bandpass filter: frequencies outside the give range of frequencies pass through; frequencies inside it are attenuated.</td><td>The center of the range of frequencies.</td><td>Controls the width of the frequency band. The greater the <code>Q</code> value, the smaller the frequency band.</td><td><em>Not used</em></td></tr><tr class="even"><td><code>allpass</code></td><td>Standard second-order <a href="https://en.wikipedia.org/wiki/All-pass_filter#Digital_Implementation">allpass</a> filter. It lets all frequencies through, but changes the phase-relationship between the various frequencies.</td><td>The frequency with the maximal <a href="https://en.wikipedia.org/wiki/Group_delay_and_phase_delay">group delay</a>, that is, the frequency where the center of the phase transition occurs.</td><td>Controls how sharp the transition is at the medium frequency. The larger this parameter is, the sharper and larger the transition will be.</td><td><em>Not used</em></td></tr></tbody></table>

## Methods

_Inherits methods from its parent, [`AudioNode`](audionode)_.

[`BiquadFilterNode.getFrequencyResponse()`](biquadfilternode/getfrequencyresponse)  
From the current filter parameter settings this method calculates the frequency response for frequencies specified in the provided array of frequencies.

## Example

See [`AudioContext.createBiquadFilter`](baseaudiocontext/createbiquadfilter#example) for example code that shows how to use an `AudioContext` to create a Biquad filter node.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#biquadfilternode">Web Audio API<br />
<span class="small">The definition of 'BiquadFilterNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

Yes

1.0

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

`Q`

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

Yes

1.0

`detune`

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

Yes

1.0

`frequency`

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

Yes

1.0

`gain`

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

Yes

1.0

`getFrequencyResponse`

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

Yes

1.0

`type`

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

Yes

1.0

## See also

- [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BiquadFilterNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BiquadFilterNode</a>
