# EffectTiming.delay

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`EffectTiming`](../effecttiming) dictionary's `delay` property in the [Web Animations API](../web_animations_api) represents the number of milliseconds to delay the start of the animation.

[`Element.animate()`](../element/animate), [`KeyframeEffectReadOnly()`](../keyframeeffect/keyframeeffect), and [`KeyframeEffect()`](../keyframeeffect/keyframeeffect) all accept an object of timing properties including `delay`. The value of `delay` corresponds directly to [`EffectTiming.delay`](delay) in [`timing`](../animationeffect/gettiming) objects returned by [`AnimationEffectReadOnly`](../animationeffect), [`KeyframeEffectReadOnly`](../keyframeeffect), and [`KeyframeEffect`](../keyframeeffect).

## Syntax

    var timingProperties = {
      delay: delayInMilliseconds
    };

    timingProperties.delay = delayInMilliseconds;

### Value

A number specifying the delay, in milliseconds, from the start of the animation's play cycle to the beginning of its **active interval** (the time index at which actual animation begins). Defaults to 0.

## Examples

In the [Pool of Tears](https://codepen.io/rachelnabors/pen/EPJdJx?editors=0010) example, each tear is passed a random delay via its timing object:

    // Randomizer function
    var getRandomMsRange = function(min, max) {
      return Math.random() * (max - min) + min;
    }

    // Loop through each tear
    tears.forEach(function(el) {

      // Animate each tear
      el.animate(
        tearsFalling,
        {
          delay: getRandomMsRange(-1000, 1000), // randomized for each tear
          duration: getRandomMsRange(2000, 6000), // randomized for each tear
          iterations: Infinity,
          easing: "cubic-bezier(0.6, 0.04, 0.98, 0.335)"
        });
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#dom-effecttiming-delay">Web Animations<br />
<span class="small">The definition of 'delay' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`delay`

52

≤79

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
- The value of this property corresponds to the one in [`EffectTiming`](../effecttiming) (which is the [`timing`](../animationeffect/gettiming) object for [`AnimationEffectReadOnly`](../animationeffect), [`KeyframeEffectReadOnly`](../keyframeeffect), and [`KeyframeEffect`](../keyframeeffect)).
- CSS's `transition-delay` and `animation-delay`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming/delay" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming/delay</a>
