# EffectTiming.duration

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `duration` property of the dictionary [`EffectTiming`](../effecttiming) in the [Web Animations API](../web_animations_api) specifies the duration in milliseconds that a single iteration (from beginning to end) the animation should take to complete.

[`Element.animate()`](../element/animate), [`KeyframeEffectReadOnly()`](../keyframeeffect/keyframeeffect), and [`KeyframeEffect()`](../keyframeeffect/keyframeeffect) all accept an object of timing properties including `duration`. The value of `duration` corresponds directly to <span class="page-not-created">`AnimationEffectTimingReadOnly.duration`</span> in [`timing`](../animationeffect/gettiming) objects returned by [`AnimationEffectReadOnly`](../animationeffect), [`KeyframeEffectReadOnly`](../keyframeeffect), and [`KeyframeEffect`](../keyframeeffect).

## Syntax

    var timingProperties = {
      duration: durationInMilliseconds | "auto"
    };

    timingProperties.duration = durationInMilliseconds | "auto";

### Value

The number of milliseconds long a single beginning-to-end iteration of the animation should take. The default is `"auto"`. This value must not be negative; otherwise, it can have any value (including positive infinity).

Currently, a value of `"auto"` is the same as specifying 0.0. This is a forwards-compatibility measure since in the future, "auto" will be expanded to take into account the duration of any child effects. Consider using `"auto"` rather than 0 if that makes sense.

### Exceptions

`TypeError`  
The specified value is either a string other than `"auto"`, a number less than zero, [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN), or some other type of object entirely.

## Examples

In the [Pool of Tears](https://codepen.io/rachelnabors/pen/EPJdJx?editors=0010) example, each tear is passed a random `duration` via its timing object:

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#iteration-duration">Web Animations<br />
<span class="small">The definition of 'duration' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`duration`

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
- The value of this property corresponds to property of the same name in [`AnimationEffectReadOnly.timing`](../animationeffect/gettiming), <span class="page-not-created">`KeyframeEffectReadOnly.timing`</span>, and <span class="page-not-created">`KeyframeEffect.timing`</span>).
- CSS's [`transition-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration) and [`animation-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration) properties

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming/duration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming/duration</a>
