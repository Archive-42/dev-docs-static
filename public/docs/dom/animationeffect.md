# AnimationEffect

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `AnimationEffect` interface of the [Web Animations API](web_animations_api) defines current and future _animation effects_ like [`KeyframeEffect`](keyframeeffect), which can be passed to [`Animation`](animation) objects for playing, and [`KeyframeEffect`](keyframeeffect) (which is used by [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) and [Transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions)).

## Methods

[`AnimationEffect.getTiming()`](animationeffect/gettiming)  
Returns the [`EffectTiming`](effecttiming) object associated with the animation containing all the animation's timing values.

[`AnimationEffect.getComputedTiming()`](animationeffect/getcomputedtiming)  
Returns the calculated timing properties for this `AnimationEffect`.

[`AnimationEffect.updateTiming()`](animationeffect/updatetiming)  
Updates the specified timing properties of this `AnimationEffect`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#the-animationeffect-interface">Web Animations<br />
<span class="small">The definition of 'AnimationEffect' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`AnimationEffect`

75

79

63

48-63

No

62

13.1

75

75

63

48-63

54

13.4

11.0

`getComputedTiming`

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

`getTiming`

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

`updateTiming`

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

- [Web Animations API](web_animations_api)
- [`Animation.effect`](animation/effect)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnimationEffect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnimationEffect</a>
