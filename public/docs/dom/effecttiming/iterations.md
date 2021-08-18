# EffectTiming.iterations

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [Web Animations API](../web_animations_api) dictionary [`EffectTiming`](../effecttiming)'s `iterations` property specifies the number of times the animation should repeat. The default value is 1, indicating that it should only play once, but you can set it to any floating-point value (including positive [`Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity) defaults to `1`, and can also take a value of `Infinity` to make it loop infinitely.

[`Element.animate()`](../element/animate), [`KeyframeEffectReadOnly()`](../keyframeeffect/keyframeeffect), and [`KeyframeEffect()`](../keyframeeffect/keyframeeffect) all accept an object of timing properties including `iterations`. The value of `iterations` corresponds directly to <span class="page-not-created">`AnimationEffectTimingReadOnly.iterations`</span> in [`timing`](../animationeffect/gettiming) objects returned by [`AnimationEffectReadOnly`](../animationeffect), [`KeyframeEffectReadOnly`](../keyframeeffect), and [`KeyframeEffect`](../keyframeeffect).

## Syntax

    var timingProperties = {
      iterations: numberOfIterations
    };

    timingProperties.iterations = numberOfIterations;

### Value

A floating-point value specifying the number of times the animation sequence will play through. Any value from 0 (don't play the animation at all) to positive [`Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity) (run the animation indefinitely) is supported. Defaults to 1, meaning the animation sequence plays through once then stops automatically.

### Exceptions

`TypeError`  
An attempt was made to set the value of this property to a negative number or [`NaN`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NaN). The property's value is left unchanged.

## Examples

In the [Forgotten Key](https://codepen.io/rachelnabors/pen/bEPdQr?editors=0010) example, Alice waves her arm up and down the entire time the page is open by passing `Infinity` as the value for her `iterations` property:

    // Get Alice's arm, and wave it up and down
    document.getElementById("alice_arm").animate([
      { transform: 'rotate(10deg)' },
      { transform: 'rotate(-40deg)' }
    ], {
      easing: 'steps(2, end)',
      iterations: Infinity,
      direction: 'alternate',
      duration: 600
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#iteration-count">Web Animations<br />
<span class="small">The definition of 'iterations' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`iterations`

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
- The value of this property corresponds to the one in <span class="page-not-created">`AnimationEffectTimingReadOnly`</span> (which is the [`timing`](../animationeffect/gettiming) object for [`AnimationEffectReadOnly`](../animationeffect), [`KeyframeEffectReadOnly`](../keyframeeffect), and [`KeyframeEffect`](../keyframeeffect)).
- CSS's [`animation-iteration-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming/iterations" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming/iterations</a>
