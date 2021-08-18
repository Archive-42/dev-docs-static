# Animation.pending

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The read-only ` Animation``.pending ` property of the [Web Animations API](../web_animations_api) indicates whether the animation is currently waiting for an asynchronous operation such as initiating playback or pausing a running animation.

## Syntax

    var pending = Animation.pending;

### Value

`true` if the animation is pending, `false` otherwise.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-currenttime">Web Animations<br />
<span class="small">The definition of 'pending' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`pending`

No

No

59

Prior to version 59, the pending status was reported by a `"pending"` value returned from [`Animation.playState`](https://developer.mozilla.org/docs/Web/API/Animation/playState).

No

No

13.1

No

No

59

Prior to version 59, the pending status was reported by a `"pending"` value returned from [`Animation.playState`](https://developer.mozilla.org/docs/Web/API/Animation/playState).

No

13.4

No

## See also

- [`Animation`](../animation) for other methods and properties you can use to control web page animation.
- [Web Animations API](../web_animations_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/pending" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/pending</a>
