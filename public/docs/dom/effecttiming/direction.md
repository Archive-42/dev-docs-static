EffectTiming.direction
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `direction` property of the [Web Animations API](../web_animations_api) dictionary [`EffectTiming`](../effecttiming) indicates an animation's playback direction along its timeline, as well as its behavior when it reaches the end of an iteration

[`Element.animate()`](../element/animate), [`KeyframeEffectReadOnly()`](../keyframeeffect/keyframeeffect), and [`KeyframeEffect()`](../keyframeeffect/keyframeeffect) all accept an object of timing properties including `direction.` The value of `direction` corresponds directly to <span class="page-not-created">`AnimationEffectTimingReadOnly.direction`</span> in [`timing`](../animationeffect/gettiming) objects returned by [`AnimationEffectReadOnly`](../animationeffect), [`KeyframeEffectReadOnly`](../keyframeeffect), and [`KeyframeEffect`](../keyframeeffect).

Syntax
------

    var timingProperties = {
      direction: "normal" | "reverse" | "alternate" | "alternate-reverse"
    };

    timingProperties.direction = "normal" | "reverse" | "alternate" | "alternate-reverse";

### Value

A [`DOMString`](../domstring) which specifies the direction in which the animation should play as well as what to do when the playback reaches the end of the animation sequence in the current direction. It can take one of the following values, with the default being `"normal"`:

`"normal"`  
The animation runs forwards, from beginning to end, in the way we experience the flow of time.

 `"reverse`"  
The animation runs backwards, or "rewinds."

`"alternate"`  
The animation switches direction after each iteration, going forward through the animation sequence the first iteration, then backward through the sequence the second iteration, and so forth.

`"alternate-reverse"`  
Similar to "alternate", except the animation playback starts by going from the end of the animation sequence toward the beginning the first iteration, then goes forward during the second, and so forth.

Examples
--------

In the [Forgotten Key](https://codepen.io/rachelnabors/pen/bEPdQr?editors=0010) example, Alice waves her arm up and down by passing her an `alternate` value for her `direction` property:

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#enumdef-playbackdirection">Web Animations<br />
<span class="small">The definition of 'direction' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`direction`

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

See also
--------

-   [Web Animations API](../web_animations_api)
-   [`Element.animate()`](../element/animate), [`KeyframeEffectReadOnly()`](../keyframeeffect/keyframeeffect), and [`KeyframeEffect()`](../keyframeeffect/keyframeeffect) all accept an object of timing properties including this one.
-   The value of this property corresponds to the one in <span class="page-not-created">`AnimationEffectTimingReadOnly`</span> (which is the [`timing`](../animationeffect/gettiming) object for [`AnimationEffectReadOnly`](../animationeffect), [`KeyframeEffectReadOnly`](../keyframeeffect), and [`KeyframeEffect`](../keyframeeffect)).
-   CSS's `animation-direction`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming/direction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming/direction</a>
