# BaseAudioContext.listener

The `listener` property of the [`BaseAudioContext`](../baseaudiocontext) interface returns an [`AudioListener`](../audiolistener) object that can then be used for implementing 3D audio spatialization.

## Syntax

    baseAudioContext.listener;

### Value

An [`AudioListener`](../audiolistener) object.

## Example

**Note**: for a full Web Audio spatialization example, see our [panner-node](https://github.com/mdn/panner-node) demo.

    var AudioContext = window.AudioContext || window.webkitAudioContext;
    var audioCtx = new AudioContext();
    // Older webkit/blink browsers require a prefix

    ...

    var myListener = audioCtx.listener;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-baseaudiocontext-listener">Web Audio API<br />
<span class="small">The definition of 'listener' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`listener`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/listener" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BaseAudioContext/listener</a>
