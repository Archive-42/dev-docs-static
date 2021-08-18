# BiquadFilterNode.frequency

The `frequency` property of the [`BiquadFilterNode`](../biquadfilternode) interface Is a [a-rate](../audioparam#a-rate) [`AudioParam`](../audioparam), a double representing a frequency in the current filtering algorithm measured in hertz (Hz).

`frequency`'s default value is `350` with a nominal range of `10` to the [Nyquist frequency](https://en.wikipedia.org/wiki/Nyquist_frequency) — that is, half of the sample rate.

## Syntax

    var audioCtx = new AudioContext();
    var biquadFilter = audioCtx.createBiquadFilter();
    biquadFilter.frequency.value = 3000;

**Note**: Though the `AudioParam` returned is read-only, the value it represents is not.

### Value

An [`AudioParam`](../audioparam).

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-biquadfilternode-frequency">Web Audio API<br />
<span class="small">The definition of 'frequency' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BiquadFilterNode/frequency" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BiquadFilterNode/frequency</a>
