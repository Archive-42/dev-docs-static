# AudioNode.context

The read-only `context` property of the [`AudioNode`](../audionode) interface returns the associated [`BaseAudioContext`](../baseaudiocontext), that is the object representing the processing graph the node is participating in.

## Syntax

    var aContext = anAudioNode.context;

### Value

The [`AudioContext`](../audiocontext) or [`OfflineAudioContext`](../offlineaudiocontext) object that was used to construct this `AudioNode`.

## Example

    const AudioContext = window.AudioContext || window.webkitAudioContext;
    const audioCtx = new AudioContext();

    const oscillator = audioCtx.createOscillator();
    const gainNode = audioCtx.createGain();
    oscillator.connect(gainNode).connect(audioCtx.destination);

    console.log(oscillator.context); // AudioContext
    console.log(oscillator.context === audioCtx); // true

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audionode-context">Web Audio API<br />
<span class="small">The definition of 'context' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/context" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioNode/context</a>
