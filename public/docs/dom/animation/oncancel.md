# Animation.oncancel

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `oncancel` property of the [Web Animations API](../web_animations_api)'s [`Animation`](../animation) interface is the event handler for the `cancel` event.

The `cancel` event can be triggered manually with [`Animation.cancel()`](cancel) when the animation enters the `"idle"` play state from another state, such as when the animation is removed from an element before it finishes playing

Creating a new animation that is initially idle does not trigger a `cancel` event on the new animation.

## Syntax

    var cancelHandler = Animation.oncancel;

    Animation.oncancel = cancelHandler;

### Value

A function to be executed when the animation is cancelled, or `null` if there is no `cancel` event handler.

## Examples

If this animation is canceled, remove its element.

    animation.oncancel = function() { animation.effect.target.remove(); };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-oncancel">Web Animations<br />
<span class="small">The definition of 'Animation.oncancel' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`oncancel`

50

79

48

No

37

13.1

50

50

48

37

13.4

5.0

## See also

- [Web Animations API](../web_animations_api)
- [`Animation`](../animation)
- The `cancel` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/oncancel" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/oncancel</a>
