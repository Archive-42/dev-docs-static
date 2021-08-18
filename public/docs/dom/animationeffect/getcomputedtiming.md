# AnimationEffect.getComputedTiming()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `getComputedTiming()` method of the [`AnimationEffect`](../animationeffect) interface returns the calculated timing properties for this animation effect.

Although many of the attributes of the returned object are common to the [`EffectTiming`](../effecttiming) contained in the object returned by the [`AnimationEffect.getTiming()`](gettiming) method, the values returned by this object differ in the following ways:

`duration`  
Returns the calculated value of the iteration duration. If [`EffectTiming.duration`](../effecttiming/duration) is the string `auto`, this attribute will return `0`.

`fill`  
The `auto` value is replaced with the appropriate [`EffectTiming.fill`](../effecttiming/fill) value.

These values are comparable to the computed styles of an Element returned using `window.getComputedStyle(elem)`.

## Syntax

    var currentTimeValues = animation.getComputedTiming();

### Parameters

None.

### Return Value

A `ComputedEffectTiming` dictionary object, which contains the following properties:

endTime  
The end time of the animation in milliseconds from the animation's start (if the [`KeyframeEffect`](../keyframeeffect) is associated with an [`Animation`](../animation)). (Also includes [`EffectTiming.endDelay`](../effecttiming/enddelay) in that calculation.)

activeDuration  
The length of time in milliseconds that the animation's effects will run. This is equal to the [iteration duration](../effecttiming/duration) multiplied by the [iteration count](../effecttiming/iterations).

localTime  
The [current time](../animationtimeline/currenttime) of the animation in milliseconds. If the `KeyframeEffect` is not associated with an `Animation`, its value is `null`.

progress  
Indicates how far along the animation is through its current iteration with values between `0` and `1`. Returns `null` if the animation is not running or its `KeyframeEffect` isn't associated with an `Animation`.

currentIteration  
The number of times this animation has looped, starting from `0`. Returns `null` if the animation is not running or its `KeyframeEffect` isn't associated with an `Animation`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-animationeffect-getcomputedtiming">Web Animations<br />
<span class="small">The definition of 'AnimationEffect.getComputedTiming()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

## See also

- [Web Animations API](../web_animations_api)
- [`AnimationEffect`](../animationeffect)
- [`Animation`](../animation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnimationEffect/getComputedTiming" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnimationEffect/getComputedTiming</a>
