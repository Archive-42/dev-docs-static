# Animation.cancel()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The Web Animations API's `cancel()` method of the [`Animation`](../animation) interface clears all [`KeyframeEffect`](../keyframeeffect)s caused by this animation and aborts its playback.

When an animation is cancelled, its [`startTime`](starttime) and [`currentTime`](currenttime) are set to `null`.

## Syntax

    Animation.cancel();

### Parameters

None.

### Return value

None.

### Exceptions

This method doesn't directly throw exceptions; however, if the animation's [`playState`](playstate) is anything but `"idle"` when cancelled, the [current finished promise](finished) is rejected with a [`DOMException`](../domexception) named `AbortError`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-cancel">Web Animations<br />
<span class="small">The definition of 'Animation.cancel()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`cancel`

39

79

48

No

26

13.1

39

39

48

26

13.4

4.0

## See also

- [Web Animations API](../web_animations_api)
- [`KeyframeEffect`](../keyframeeffect)
- [`Animation`](../animation)
- [`Animation.playState`](playstate)
- [`Animation.finished`](finished) returns the promise this action will reject if the animation's `playState` is not `"idle"`.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/cancel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/cancel</a>
