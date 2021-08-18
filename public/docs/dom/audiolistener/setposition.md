# AudioListener.setPosition()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `setPosition()` method of the [`AudioListener`](../audiolistener) Interface defines the position of the listener.

The three parameters `x`, `y` and `z` are unitless and describe the listener's position in 3D space according to the right-hand Cartesian coordinate system. [`PannerNode`](../pannernode) objects use this position relative to individual audio sources for spatialisation.

The default value of the position vector is `(0,` `0,` `0)`.

## Syntax

    var audioCtx = new AudioContext();
    var myListener = audioCtx.listener;
    myListener.setPosition(1,1,1);

### Returns

Void.

## Example

See [`BaseAudioContext.createPanner()`](../baseaudiocontext/createpanner#example) for example code.

## Parameters

x  
The x position of the listener in 3D space.

y  
The y position of the listener in 3D space.

z  
The z position of the listener in 3D space.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-audiolistener-setposition">Web Audio API<br />
<span class="small">The definition of 'setPosition()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`setPosition`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/setPosition" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/setPosition</a>
