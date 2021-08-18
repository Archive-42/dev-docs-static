# AudioListener.setOrientation()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `setOrientation()` method of the [`AudioListener`](../audiolistener) interface defines the orientation of the listener.

It consists of two direction vectors:

- The _front vector_, defined by the three unitless parameters `x`, `y` and `z`, describes the direction of the face of the listener, that is the direction the nose of the person is pointing towards. The front vector's default value is `(0,` `0,` `-1)`.
- The _up vector_, defined by three unitless parameters `xUp`, `yUp` and `zUp`, describes the direction of the top of the listener's head. The up vector's default value is `(0,` `1,` `0)`.

The two vectors must be separated by an angle of 90° — in linear analysis terms, they must be perpendicular to each other.

## Syntax

    var audioCtx = new AudioContext();
    var myListener = audioCtx.listener;
    myListener.setOrientation(0,0,-1,0,1,0);

### Returns

Void.

## Example

See [`BaseAudioContext.createPanner()`](../baseaudiocontext/createpanner#example) for example code.

## Parameters

x  
The x value of the front vector of the listener.

y  
The y value of the front vector of the listener.

z  
The z value of the front vector of the listener.

xUp  
The x value of the up vector of the listener.

yUp  
The y value of the up vector of the listener.

zUp  
The z value of the up vector of the listener.

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

`setOrientation`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/setOrientation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AudioListener/setOrientation</a>
