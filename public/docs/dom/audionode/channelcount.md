# AudioNode.channelCount

The `channelCount` property of the [`AudioNode`](../audionode) interface represents an integer used to determine how many channels are used when [up-mixing and down-mixing](../web_audio_api/basic_concepts_behind_web_audio_api#up-mixing_and_down-mixing) connections to any inputs to the node.

`channelCount`'s usage and precise definition depend on the value of [`AudioNode.channelCountMode`](channelcountmode):

- It is ignored if the `channelCountMode` value is `max`.
- It is used as a maximum value if the `channelCountMode` value is `clamped-max`.
- It is used as the exact value if the `channelCountMode` value is `explicit`.

## Syntax

    var oscillator = audioCtx.createOscillator();
    var channels = oscillator.channelCount;

### Value

An integer.

## Example

    var AudioContext = window.AudioContext || window.webkitAudioContext;

    var audioCtx = new AudioContext();

    var oscillator = audioCtx.createOscillator();
    var gainNode = audioCtx.createGain();

    oscillator.connect(gainNode);
    gainNode.connect(audioCtx.destination);

    oscillator.channelCount;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audionode-channelcount">Web Audio API<br />
<span class="small">The definition of 'channelCount' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/channelCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/channelCount</a>
