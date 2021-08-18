# AudioParam.defaultValue

The `defaultValue` read-only property of the [`AudioParam`](../audioparam) interface represents the initial value of the attributes as defined by the specific [`AudioNode`](../audionode) creating the `AudioParam`.

## Syntax

    var defaultVal = audioParam.defaultValue;

### Value

A floating-point [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number).

## Example

    const audioCtx = new AudioContext();
    const gainNode = audioCtx.createGain();
    const defaultVal = gainNode.gain.defaultValue;
    console.log(defaultVal); // 1
    console.log(defaultVal === gainNode.gain.value); // true

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audioparam-defaultvalue">Web Audio API<br />
<span class="small">The definition of 'defaultValue' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`defaultValue`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/defaultValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioParam/defaultValue</a>
