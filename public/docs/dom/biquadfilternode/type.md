# BiquadFilterNode.type

The `type` property of the [`BiquadFilterNode`](../biquadfilternode) interface is a string (enum) value defining the kind of filtering algorithm the node is implementing.

## Syntax

    var audioCtx = new AudioContext();
    var biquadFilter = audioCtx.createBiquadFilter();
    biquadFilter.type = 'lowpass';

### Value

A string (enum) representing a [BiquadFilterType](https://webaudio.github.io/web-audio-api/#idl-def-BiquadFilterType).

## `type` values and their meaning

<table><thead><tr class="header"><th><code>type</code></th><th>Description</th><th><code>frequency</code></th><th><code>Q</code></th><th><code>gain</code></th></tr></thead><tbody><tr class="odd"><td><code>lowpass</code></td><td>Standard second-order resonant lowpass filter with 12dB/octave rolloff. Frequencies below the cutoff pass through; frequencies above it are attenuated.</td><td>The cutoff frequency.</td><td>Indicates how peaked the frequency is around the cutoff. The greater the value is, the greater is the peak.</td><td><em>Not used</em></td></tr><tr class="even"><td><code>highpass</code></td><td>Standard second-order resonant highpass filter with 12dB/octave rolloff. Frequencies below the cutoff are attenuated; frequencies above it pass through.</td><td>The cutoff frequency.</td><td>Indicates how peaked the frequency is around the cutoff. The greater the value, the greater the peak.</td><td><em>Not used</em></td></tr><tr class="odd"><td><code>bandpass</code></td><td>Standard second-order bandpass filter. Frequencies outside the given range of frequencies are attenuated; the frequencies inside it pass through.</td><td>The center of the range of frequencies.</td><td>Controls the width of the frequency band. The greater the <code>Q</code> value, the larger the frequency band.</td><td><em>Not used</em></td></tr><tr class="even"><td><code>lowshelf</code></td><td>Standard second-order lowshelf filer. Frequencies lower than the frequency get a boost, or an attenuation; frequencies over it are unchanged.</td><td>The upper limit of the frequencies getting a boost or an attenuation.</td><td><em>Not used</em></td><td>The boost, in dB, to be applied; if negative, it will be an attenuation.</td></tr><tr class="odd"><td><code>highshelf</code></td><td>Standard second-order highshelf filer. Frequencies higher than the frequency get a boost or an attenuation; frequencies lower than it are unchanged.</td><td>The lower limit of the frequencies getting a boost or an attenuation.</td><td><em>Not used</em></td><td>The boost, in dB, to be applied; if negative, it will be an attenuation.</td></tr><tr class="even"><td><code>peaking</code></td><td>Frequencies inside the range get a boost or an attenuation; frequencies outside it are unchanged.</td><td>The middle of the frequency range getting a boost or an attenuation.</td><td>Controls the width of the frequency band. The greater the <code>Q</code> value, the larger the frequency band.</td><td>The boost, in dB, to be applied; if negative, it will be an attenuation.</td></tr><tr class="odd"><td><code>notch</code></td><td>Standard <a href="https://en.wikipedia.org/wiki/Band-stop_filter">notch</a> filter, also called a <em>band-stop</em> or <em>band-rejection</em> filter. It is the opposite of a bandpass filter: frequencies outside the give range of frequencies pass through; frequencies inside it are attenuated.</td><td>The center of the range of frequencies.</td><td>Controls the width of the frequency band. The greater the <code>Q</code> value, the larger the frequency band.</td><td><em>Not used</em></td></tr><tr class="even"><td><code>allpass</code></td><td>Standard second-order <a href="https://en.wikipedia.org/wiki/All-pass_filter#Digital_Implementation">allpass</a> filter. It Lets all frequencies through, but changes the phase-relationship between the various frequencies.</td><td>The frequency with the maximal <a href="https://en.wikipedia.org/wiki/Group_delay_and_phase_delay">group delay</a>, that is, the frequency where the center of the phase transition occurs.</td><td>Controls how sharp the transition is at the medium frequency. The larger this parameter is, the sharper and larger the transition will be.</td><td><em>Not used</em></td></tr></tbody></table>

## Example

The following example shows basic usage of an AudioContext to create a Biquad filter node. For a complete working example, check out our [voice-change-o-matic](https://mdn.github.io/voice-change-o-matic/) demo (look at the [source code](https://github.com/mdn/voice-change-o-matic) too).

    var audioCtx = new (window.AudioContext || window.webkitAudioContext)();

    //set up the different audio nodes we will use for the app
    var analyser = audioCtx.createAnalyser();
    var distortion = audioCtx.createWaveShaper();
    var gainNode = audioCtx.createGain();
    var biquadFilter = audioCtx.createBiquadFilter();
    var convolver = audioCtx.createConvolver();

    // connect the nodes together

    source = audioCtx.createMediaStreamSource(stream);
    source.connect(analyser);
    analyser.connect(distortion);
    distortion.connect(biquadFilter);
    biquadFilter.connect(convolver);
    convolver.connect(gainNode);
    gainNode.connect(audioCtx.destination);

    // Manipulate the Biquad filter

    biquadFilter.type = "lowshelf";
    biquadFilter.frequency.value = 1000;
    biquadFilter.gain.value = 25;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-biquadfilternode-type">Web Audio API<br />
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

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BiquadFilterNode/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BiquadFilterNode/type</a>
