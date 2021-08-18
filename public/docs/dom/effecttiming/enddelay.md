# EffectTiming.endDelay

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `endDelay` property of the [`EffectTiming`](../effecttiming) dictionary (part of the [Web Animations API](../web_animations_api)) indicates the number of milliseconds to delay after the active period of an animation sequence. The animation's **end time**—the time at which an iteration is considered to have finished—is the time at which the animation finishes an iteration (its initial delay, <span class="page-not-created">`AnimationEffectTimingReadOnly.delay`</span>, plus its duration,<span class="page-not-created">`duration`</span>, plus its end delay.

This is useful for sequencing animations based on the end time of another animation; note, however, that many of the sequence effects that will benefit most from this property have not been defined in the specification yet. For now, its main purpose is to represent the value of the [SVG](https://developer.mozilla.org/en-US/docs/Web/SVG) `min` attribute.

[`Element.animate()`](../element/animate), [`KeyframeEffectReadOnly()`](../keyframeeffect/keyframeeffect), and [`KeyframeEffect()`](../keyframeeffect/keyframeeffect) all accept an object of timing properties including `endDelay.` The value of `endDelay` corresponds directly to <span class="page-not-created">`AnimationEffectTimingReadOnly.endDelay`</span> in [`timing`](../animationeffect/gettiming) objects returned by [`AnimationEffectReadOnly`](../animationeffect), [`KeyframeEffectReadOnly`](../keyframeeffect), and [`KeyframeEffect`](../keyframeeffect).

## Syntax

    var timingProperties = {
      endDelay: delayInMilliseconds
    }

    timingProperties.endDelay = delayInMilliseconds;

### Value

A number representing the end delay, specified in milliseconds. The default value is 0.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#end-delay">Web Animations<br />
<span class="small">The definition of 'endDelay' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`endDelay`

52

79

63

No

Yes

No

52

52

63

No

No

6.0

## See also

- [Web Animations API](../web_animations_api)
- [`Element.animate()`](../element/animate), [`KeyframeEffectReadOnly()`](../keyframeeffect/keyframeeffect), and [`KeyframeEffect()`](../keyframeeffect/keyframeeffect) all accept an object of timing properties including this one.
- The value of this property corresponds to the one in <span class="page-not-created">`AnimationEffectTimingReadOnly`</span> (which is the [`timing`](../animationeffect/gettiming) object for [`AnimationEffectReadOnly`](../animationeffect), [`KeyframeEffectReadOnly`](../keyframeeffect), and [`KeyframeEffect`](../keyframeeffect)).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming/endDelay" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming/endDelay</a>
