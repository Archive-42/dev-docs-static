# Animation.id

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The ` Animation``.id ` property of the [Web Animations API](../web_animations_api) returns or sets a string used to identify the animation.

## Syntax

    var animationsId = Animation.id;

    Animation.id = newIdString;

### Value

A [`DOMString`](../domstring) which can be used to identify the animation, or `null` if the animation has no `id`.

## Examples

In the [Follow the White Rabbit example](https://codepen.io/rachelnabors/pen/eJyWzm?editors=0010), you can assign the `rabbitDownAnimation` an `id` like so:

    rabbitDownAnimation.effect.id = "rabbitGo";

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-id">Web Animations<br />
<span class="small">The definition of 'Animation.id' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`id`

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

- [`KeyframeEffect`](../keyframeeffect)
- [Web Animations API](../web_animations_api)
- [`Animation`](../animation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/id" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/id</a>
