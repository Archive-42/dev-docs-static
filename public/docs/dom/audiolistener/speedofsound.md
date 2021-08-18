# AudioListener.speedOfSound

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `speedOfSound` property of the [`AudioListener`](../audiolistener) interface is a double value representing the speed of sound, in _meters per second_.

The `speedOfSound` property's default value is `343.3` m/s and is used to calculate the [doppler shift](https://en.wikipedia.org/wiki/Doppler_effect) appropriate for the speed the panner is travelling at (as defined by [`PannerNode.setVelocity`](../pannernode/setvelocity).)

**Note**: Bear in mind that no propagation delay is automatically applied to a sound far from the listener.

## Syntax

    var audioCtx = new AudioContext();
    var myListener = audioCtx.listener;
    myListener.speedOfSound = 343.3;

### Value

A double.

## Example

See [`BaseAudioContext.createPanner()`](../baseaudiocontext/createpanner#example) for example code.

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

`speedOfSound`

14-56

12-79

25-63

No

15-43

6-14.1

≤37-56

18-56

25-63

14-43

6-14.5

1.0-6.0

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/speedOfSound" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/speedOfSound</a>
