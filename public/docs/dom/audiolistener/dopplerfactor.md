# AudioListener.dopplerFactor

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The deprecated `dopplerFactor` property of the [`AudioListener`](../audiolistener) interface is a double value representing the amount of pitch shift to use when rendering a [doppler effect](https://en.wikipedia.org/wiki/Doppler_effect).

The `dopplerFactor` property's default value is `1`, which is a sensible default for most situations.

## Syntax

    var audioCtx = new AudioContext();
    var myListener = audioCtx.listener;
    myListener.dopplerFactor = 1;

### Value

A double indicating the doppler effect's pitch shift value. The value is 1 by default.

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

`dopplerFactor`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/dopplerFactor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/dopplerFactor</a>
