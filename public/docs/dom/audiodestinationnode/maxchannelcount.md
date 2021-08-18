# AudioDestinationNode.maxChannelCount

The `maxchannelCount` property of the [`AudioDestinationNode`](../audiodestinationnode) interface is an `unsigned long` defining the maximum amount of channels that the physical device can handle.

The [`AudioNode.channelCount`](../audionode/channelcount) property can be set between 0 and this value (both included). If `maxChannelCount` is `0`, like in [`OfflineAudioContext`](../offlineaudiocontext), the channel count cannot be changed.

## Syntax

    var audioCtx = new AudioContext();
    var myDestination = audioCtx.destination;
    myDestination.maxChannelCount = 2;

### Value

An `unsigned long`.

## Example

The following would set up a simple audio graph, featuring an `AudioDestinationNode` with `maxChannelCount` of 2:

    var audioCtx = new AudioContext();
    var source = audioCtx.createMediaElementSource(myMediaElement);
    source.connect(gainNode);
    audioCtx.destination.maxChannelCount = 2;
    gainNode.connect(audioCtx.destination);

To see a more complete implementation, check out one of our MDN Web Audio examples, such as [Voice-change-o-matic](https://mdn.github.io/voice-change-o-matic/) or [Violent Theremin](https://mdn.github.io/violent-theremin/).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiodestinationnode-maxchannelcount">Web Audio API<br />
<span class="small">The definition of 'maxChannelCount' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioDestinationNode/maxChannelCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioDestinationNode/maxChannelCount</a>
