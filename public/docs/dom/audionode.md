# AudioNode

The `AudioNode` interface is a generic interface for representing an audio processing module.

Examples include:

- an audio source (e.g. an HTML [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, an [`OscillatorNode`](oscillatornode), etc.),
- the audio destination,
- intermediate processing module (e.g. a filter like [`BiquadFilterNode`](biquadfilternode) or [`ConvolverNode`](convolvernode)), or
- volume control (like [`GainNode`](gainnode))

**Note**: An `AudioNode` can be target of events, therefore it implements the [`EventTarget`](eventtarget) interface.

## Description

### The audio routing graph

<img src="data:image/png;base64,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" alt="AudioNodes participating in an AudioContext create a audio routing graph." width="677" height="461" />

Each `AudioNode` has inputs and outputs, and multiple audio nodes are connected to build a _processing graph_. This graph is contained in an [`AudioContext`](audiocontext), and each audio node can only belong to one audio context.

A _source node_ has zero inputs but one or multiple outputs, and can be used to generate sound. On the other hand, a _destination node_ has no outputs; instead, all its inputs are directly played back on the speakers (or whatever audio output device the audio context uses). In addition, there are _processing nodes_ which have inputs and outputs. The exact processing done varies from one `AudioNode` to another but, in general, a node reads its inputs, does some audio-related processing, and generates new values for its outputs, or lets the audio pass through (for example in the [`AnalyserNode`](analysernode), where the result of the processing is accessed separately).

The more nodes in a graph, the higher the latency will be. For example, if your graph has a latency of 500ms, when the source node plays a sound, it will take half a second until that sound can be heard on your speakers (or even longer because of latency in the underlying audio device). Therefore, if you need to have interactive audio, keep the graph as small as possible, and put user-controlled audio nodes at the end of a graph. For example, a volume control (`GainNode`) should be the last node so that volume changes take immediate effect.

Each input and output has a given amount of _channels_. For example, mono audio has one channel, while stereo audio has two channels. The Web Audio API will up-mix or down-mix the number of channels as required; check the Web Audio spec for details.

For a list of all audio nodes, see the [Web Audio API](web_audio_api) homepage.

### Creating an `AudioNode`

There are two ways to create an `AudioNode`: via the _constructor_ and via the _factory method_.

    // constructor
    const analyserNode = new AnalyserNode(audioCtx, {
      fftSize: 2048,
      maxDecibels: -25,
      minDecibels: -60,
      smoothingTimeConstant: 0.5,
    });

    // factory method
    const analyserNode = audioCtx.createAnalyser();
    analyserNode.fftSize = 2048;
    analyserNode.maxDecibels = -25;
    analyserNode.minDecibels = -60;
    analyserNode.smoothingTimeConstant = 0.5;

You are free to use either constructors or factory methods, or mix both, however there are advantages to using the constructors:

- All parameters can be set during construction time and don't need to be set individually.
- You can [sub-class an audio node](https://github.com/WebAudio/web-audio-api/issues/251). While the actual processing is done internally by the browser and cannot be altered, you could write a wrapper around an audio node to provide custom properties and methods.
- Slightly better performance: In both Chrome and Firefox, the factory methods call the constructors internally.

Keep in mind that Microsoft Edge does not yet appear to support the constructors; it will throw a "Function expected" error when you use the constructors.

_Brief history:_ The first version of the Web Audio spec only defined the factory methods. After a [design review in October 2013](https://github.com/WebAudio/web-audio-api/issues/250), it was decided to add constructors because they have numerous benefits over factory methods. The constructors were added to the spec from August to October 2016. Factory methods continue to be included in the spec and are not deprecated.

## Properties

[`AudioNode.context`](audionode/context) <span class="badge inline readonly">Read only </span>  
Returns the associated [`BaseAudioContext`](baseaudiocontext), that is the object representing the processing graph the node is participating in.

[`AudioNode.numberOfInputs`](audionode/numberofinputs) <span class="badge inline readonly">Read only </span>  
Returns the number of inputs feeding the node. Source nodes are defined as nodes having a `numberOfInputs` property with a value of `0`.

[`AudioNode.numberOfOutputs`](audionode/numberofoutputs) <span class="badge inline readonly">Read only </span>  
Returns the number of outputs coming out of the node. Destination nodes — like [`AudioDestinationNode`](audiodestinationnode) — have a value of `0` for this attribute.

[`AudioNode.channelCount`](audionode/channelcount)  
Represents an integer used to determine how many channels are used when [up-mixing and down-mixing](web_audio_api/basic_concepts_behind_web_audio_api#up-mixing_and_down-mixing) connections to any inputs to the node. Its usage and precise definition depend on the value of [`AudioNode.channelCountMode`](audionode/channelcountmode).

[`AudioNode.channelCountMode`](audionode/channelcountmode)  
Represents an enumerated value describing the way channels must be matched between the node's inputs and outputs.

[`AudioNode.channelInterpretation`](audionode/channelinterpretation)  
Represents an enumerated value describing the meaning of the channels. This interpretation will define how audio [up-mixing and down-mixing](web_audio_api/basic_concepts_behind_web_audio_api#up-mixing_and_down-mixing) will happen.  
The possible values are `"speakers"` or `"discrete"`.

## Methods

_Also implements methods from the interface_ [`EventTarget`](eventtarget).

[`AudioNode.connect()`](audionode/connect)  
Allows us to connect the output of this node to be input into another node, either as audio data or as the value of an [`AudioParam`](audioparam).

[`AudioNode.disconnect()`](audionode/disconnect)  
Allows us to disconnect the current node from another one it is already connected to.

## Example

This simple snippet of code shows the creation of some audio nodes, and how the `AudioNode` properties and methods can be used. You can find examples of such usage on any of the examples linked to on the [Web Audio API](web_audio_api) landing page (for example [Violent Theremin](https://github.com/mdn/violent-theremin).)

    const audioCtx = new AudioContext();

    const oscillator = new OscillatorNode(audioCtx);
    const gainNode = new GainNode(audioCtx);

    oscillator.connect(gainNode).connect(audioCtx.destination);

    oscillator.context;
    oscillator.numberOfInputs;
    oscillator.numberOfOutputs;
    oscillator.channelCount;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#audionode">Web Audio API<br />
<span class="small">The definition of 'AudioNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`AudioNode`

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

`channelCount`

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

`channelCountMode`

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

`channelInterpretation`

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

`context`

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

`disconnect`

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

`numberOfInputs`

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

`numberOfOutputs`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioNode</a>
