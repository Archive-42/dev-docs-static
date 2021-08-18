EffectTiming.iterationStart
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

[Web Animations API](../web_animations_api)'s [`EffectTiming`](../effecttiming) dictionary's `iterationStart` property specifies the repetition number which repetition the animation begins at and its progress through it.

[`Element.animate()`](../element/animate), [`KeyframeEffectReadOnly.KeyframeEffectReadOnly()`](../keyframeeffect/keyframeeffect), and [`KeyframeEffect.KeyframeEffect()`](../keyframeeffect/keyframeeffect) all accept an object of timing properties including `iterationStart.` The value of `iterationStart` corresponds directly to <span class="page-not-created">`AnimationEffectTimingReadOnly.iterationStart`</span> in [`timing`](../animationeffect/gettiming) objects returned by [`AnimationEffectReadOnly`](../animationeffect), [`KeyframeEffectReadOnly`](../keyframeeffect), and [`KeyframeEffect`](../keyframeeffect).

Syntax
------

    var timingProperties = {
      iterationStart = iterationNumber
    };

    timingProperties.iterationStart = iterationNumber;

### Value

A floating-point value whose value is at least 0 and is not [`+Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity), indicating the offset into the number of iterations the animation sequence is to run at which to start animating. `iterationStart` represents the iteration index at which the animation effect begins as well as its progress through that iteration.

Usually you'll use a value between 0.0 and 1.0 to indicate an offset into the first run of the animation at which to begin the animation performance, but any positive, non-infinite value is allowed. Since all animations' iteration indexes start at 0, a value of 0.5 would start the animation halfway through its first iteration or loop. Meanwhile, a value of 1.2 means the animation will begin playback 20% of the way through its second iteration, and so forth.

It's currently undefined what happens if you specify a value of `iterationStart` which is greater than the value of [`AnimationEffectTimingProperties.iterations`](iterations). See [issue 170 in the Web Animations API specification's issue tracker](https://github.com/w3c/web-animations/issues/170) for details and status of any changes to the specification in this regard.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#iteration-start">Web Animations<br />
<span class="small">The definition of 'iterationStart' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Editor's draft.</td></tr></tbody></table>

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

`iterationStart`

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
-   The value of this property corresponds to [`AnimationEffectReadOnly.timing`](../animationeffect/gettiming), <span class="page-not-created">`KeyframeEffectReadOnly.timing`</span>, and <span class="page-not-created">`KeyframeEffect.timing`</span>).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming/iterationStart" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming/iterationStart</a>
