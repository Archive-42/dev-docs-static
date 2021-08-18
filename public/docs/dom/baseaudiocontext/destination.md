# BaseAudioContext.destination

The `destination` property of the [`BaseAudioContext`](../baseaudiocontext) interface returns an [`AudioDestinationNode`](../audiodestinationnode) representing the final destination of all audio in the context. It often represents an actual audio-rendering device such as your device's speakers.

## Syntax

    baseAudioContext.destination;

### Value

An [`AudioDestinationNode`](../audiodestinationnode).

## Example

**Note**: for a full example implementation, see one of our Web Audio Demos on the [MDN Github repo](https://github.com/mdn/), like [voice-change-o-matic](https://github.com/mdn/voice-change-o-matic).

    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();
    // Older webkit/blink browsers require a prefix

    var oscillatorNode = audioCtx.createOscillator();
    var gainNode = audioCtx.createGain();

    oscillatorNode.connect(gainNode);
    gainNode.connect(audioCtx.destination);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-destination">Web Audio API<br />
<span class="small">The definition of 'destination' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`destination`

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

6

1.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/destination" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/destination</a>
