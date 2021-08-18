# AudioNode.connect()

The `connect()` method of the [`AudioNode`](../audionode) interface lets you connect one of the node's outputs to a target, which may be either another `AudioNode` (thereby directing the sound data to the specified node) or an [`AudioParam`](../audioparam), so that the node's output data is automatically used to change the value of that parameter over time.

## Syntax

    var destinationNode = AudioNode.connect(destination, outputIndex, inputIndex);

    AudioNode.connect(destination, outputIndex);

### Parameters

`destination`  
The [`AudioNode`](../audionode) or [`AudioParam`](../audioparam) to which to connect.

`outputIndex` <span class="badge inline optional">Optional</span>  
An index specifying which output of the current `AudioNode` to connect to the destination. The index numbers are defined according to the number of output channels (see [Audio channels](../web_audio_api/basic_concepts_behind_web_audio_api#audio_channels)). While you can only connect a given output to a given input once (repeated attempts are ignored), you can connect an output to multiple inputs by calling `connect()` repeatedly. This makes [fan-out](../web_audio_api/basic_concepts_behind_web_audio_api#fan-in_and_fan-out) possible. The default value is 0.

`inputIndex` <span class="badge inline optional">Optional</span>  
An index describing which input of the destination you want to connect the current `AudioNode` to; the default is 0. The index numbers are defined according to the number of input channels (see [Audio channels](../web_audio_api/basic_concepts_behind_web_audio_api#audio_channels)). It is possible to connect an `AudioNode` to another `AudioNode`, which in turn connects back to the first `AudioNode`, creating a cycle. This is allowed only if there is at least one [`DelayNode`](../delaynode) in the cycle. Otherwise, a `NotSupportedError` exception is thrown. This parameter is not allowed if the destination is an [`AudioParam`](../audioparam).

### Return value

If the destination is a node, `connect()` returns a reference to the destination [`AudioNode`](../audionode) object, allowing you to chain multiple `connect()` calls. In some browsers, older implementations of this interface return [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

If the destination is an `AudioParam`, `connect()` returns `undefined`.

### Exceptions

`IndexSizeError`  
The value specified as `outputIndex` or `inputIndex` doesn't correspond to an existing input or output.

`InvalidAccessError`  
The destination node is not part of the same audio context as the source node.

`NotSupportedError`  
The specified connection would create a cycle (in which the audio loops back through the same nodes repeatedly) and there are no [`DelayNode`](../delaynode)s in the cycle to prevent the resulting waveform from getting stuck constructing the same audio frame indefinitely.

## Examples

### Connecting to an audio input

The most obvious use of the `connect()` method is to direct the audio output from one node into the audio input of another node for further processing. For example, you might send the audio from a [`MediaElementAudioSourceNode`](../mediaelementaudiosourcenode)—that is, the audio from an HTML5 media element such as [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)—through a band pass filter implemented using a [`BiquadFilterNode`](../biquadfilternode) to reduce noise before then sending the audio along to the speakers.

This example creates an oscillator, then links it to a gain node, so that the gain node controls the volume of the oscillator node.

    var AudioContext = window.AudioContext || window.webkitAudioContext;

    var audioCtx = new AudioContext();

    var oscillator = audioCtx.createOscillator();
    var gainNode = audioCtx.createGain();

    oscillator.connect(gainNode);
    gainNode.connect(audioCtx.destination);

### AudioParam example

In this example, we will be altering the gain value of a [`GainNode`](../gainnode) using an [`OscillatorNode`](../oscillatornode) with a slow frequency value. This technique is know as an _LFO_-controlled parameter.

    var AudioContext = window.AudioContext || window.webkitAudioContext;

    var audioCtx = new AudioContext();

    // create an normal oscillator to make sound
    var oscillator = audioCtx.createOscillator();

    // create a second oscillator that will be used as an LFO (Low-frequency
    // oscillator), and will control a parameter
    var lfo = audioCtx.createOscillator();

    // set the frequency of the second oscillator to a low number
    lfo.frequency.value = 2.0; // 2Hz: two oscillations par second

    // create a gain whose gain AudioParam will be controlled by the LFO
    var gain = audioCtx.createGain();

    // connect the LFO to the gain AudioParam. This means the value of the LFO
    // will not produce any audio, but will change the value of the gain instead
    lfo.connect(gain.gain);

    // connect the oscillator that will produce audio to the gain
    oscillator.connect(gain);

    // connect the gain to the destination so we hear sound
    gain.connect(audioCtx.destination);

    // start the oscillator that will produce audio
    oscillator.start();

    // start the oscillator that will modify the gain value
    lfo.start();

#### AudioParam notes

It is possible to connect an `AudioNode` output to more than one [`AudioParam`](../audioparam), and more than one AudioNode output to a single [`AudioParam`](../audioparam), with multiple calls to `connect()`. [Fan-in and fan-out](../web_audio_api/basic_concepts_behind_web_audio_api#fan-in_and_fan-out) are therefore supported.

An [`AudioParam`](../audioparam) will take the rendered audio data from any `AudioNode` output connected to it and convert it to mono by [down-mixing](../web_audio_api/basic_concepts_behind_web_audio_api#up-mixing_and_down-mixing) (if it is not already mono). Next, it will mix it together with any other such outputs, and the intrinsic parameter value (the value the [`AudioParam`](../audioparam) would normally have without any audio connections), including any timeline changes scheduled for the parameter.

Therefore, it is possible to choose the range in which an [`AudioParam`](../audioparam) will change by setting the value of the [`AudioParam`](../audioparam) to the central frequency, and to use a [`GainNode`](../gainnode) between the audio source and the [`AudioParam`](../audioparam) to adjust the range of the [`AudioParam`](../audioparam) changes.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audionode-connect">Web Audio API<br />
<span class="small">The definition of 'connect() to an AudioNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audionode-connect-destinationparam-output">Web Audio API<br />
<span class="small">The definition of 'connect() to an AudioParam' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`connect`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/connect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/connect</a>
