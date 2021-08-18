# Animation.effect

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The ` Animation``.effect ` property of the [Web Animations API](../web_animations_api) gets and sets the target effect of an animation. The target effect may be either an effect object of a type based on [`AnimationEffect`](../animationeffect), such as [`KeyframeEffect`](../keyframeeffect), or `null`.

## Syntax

    var effect = Animation.effect;

    Animation.effect = AnimationEffect

### Value

A [`AnimationEffect`](../animationeffect) object describing the target animation effect for the animation, or `null` to indicate no active effect.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animation-effect">Web Animations<br />
<span class="small">The definition of 'Animation.effect' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`effect`

75

79

63

No

62

13.1

75

75

63

54

13.4

11.0

## See also

- [Web Animations API](../web_animations_api)
- [`AnimationEffect`](../animationeffect)
- [`Animation`](../animation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Animation/effect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Animation/effect</a>
