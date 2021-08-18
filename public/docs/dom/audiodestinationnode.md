# AudioDestinationNode

The `AudioDestinationNode` interface represents the end destination of an audio graph in a given context — usually the speakers of your device. It can also be the node that will "record" the audio data when used with an `OfflineAudioContext`.

`AudioDestinationNode` has no output (as it _is_ the output, no more `AudioNode` can be linked after it in the audio graph) and one input. The number of channels in the input must be between `0` and the `maxChannelCount` value or an exception is raised.

The `AudioDestinationNode` of a given `AudioContext` can be retrieved using the [`AudioContext.destination`](baseaudiocontext/destination) property.

<table><tbody><tr class="odd"><td>Number of inputs</td><td><code>1</code></td></tr><tr class="even"><td>Number of outputs</td><td><code>0</code></td></tr><tr class="odd"><td>Channel count mode</td><td><code>"explicit"</code></td></tr><tr class="even"><td>Channel count</td><td><code>2</code></td></tr><tr class="odd"><td>Channel interpretation</td><td><code>"speakers"</code></td></tr></tbody></table>

## Properties

_Inherits properties from its parent, [`AudioNode`](audionode)_.

[`AudioDestinationNode.maxChannelCount`](audiodestinationnode/maxchannelcount)  
Is an `unsigned long` defining the maximum number of channels that the physical device can handle.

## Methods

_No specific method; inherits methods from its parent, [`AudioNode`](audionode)_.

## Example

There is no complex set up for using an `AudioDestinationNode` — by default, this represents the output of the user's system (e.g. their speakers), so you can get it hooked up inside an audio graph using only a few lines of code:

    var audioCtx = new AudioContext();
    var source = audioCtx.createMediaElementSource(myMediaElement);
    source.connect(gainNode);
    gainNode.connect(audioCtx.destination);

To see a more complete implementation, check out one of our MDN Web Audio examples, such as [Voice-change-o-matic](https://mdn.github.io/voice-change-o-matic/) or [Violent Theremin](https://mdn.github.io/violent-theremin/).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#AudioDestinationNode">Web Audio API<br />
<span class="small">The definition of 'AudioDestinationNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`AudioDestinationNode`

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

`maxChannelCount`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioDestinationNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioDestinationNode</a>
