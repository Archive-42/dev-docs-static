# AudioListener.positionZ

The `positionZ` read-only property of the [`AudioListener`](../audiolistener) interface is an [`AudioParam`](../audioparam) representing the z position of the listener in 3D cartesian space.

**Note**: The parameter is _a-rate_ when used with a [`PannerNode`](../pannernode) whose [`PannerNode`](../pannernode/panningmodel) is set to equalpower, or _k-rate_ otherwise.

## Syntax

    var audioCtx = new AudioContext();
    var myListener = audioCtx.listener;
    myListener.positionZ.value = 1;

### Value

An [`AudioParam`](../audioparam). Its default value is 0, and it can range between positive and negative infinity.

## Example

See [`BaseAudioContext.createPanner()`](../baseaudiocontext/createpanner#example) for example code.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiolistener-positionz">Web Audio API<br />
<span class="small">The definition of 'positionZ' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`positionZ`

52

79

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

No

39

14.1

52

52

No

Supports a deprecated way of setting orientation - the `setOrientation()` method.

41

14.5

6.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/positionZ" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/positionZ</a>
