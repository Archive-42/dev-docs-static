# EffectTiming

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `EffectTiming` dictionary, part of the [Web Animations API](web_animations_api), is used by [`Element.animate()`](element/animate), [`KeyframeEffectReadOnly()`](keyframeeffect/keyframeeffect), and [`KeyframeEffect()`](keyframeeffect/keyframeeffect) to describe timing properties for animation effects. These properties are all optional, although without setting a `duration` the animation will not play.

In other words, these properties describe how the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) should go about making the transition from keyframe to keyframe, and how to behave when the animation begins and ends.

## Properties

[`delay`](effecttiming/delay) <span class="badge inline optional">Optional</span>  
The number of milliseconds to delay the start of the animation. Defaults to 0.

[`direction`](effecttiming/direction) <span class="badge inline optional">Optional</span>  
Whether the animation runs forwards (`normal`), backwards (`reverse`), switches direction after each iteration (`alternate`), or runs backwards and switches direction after each iteration (`alternate-reverse`). Defaults to `"normal"`.

[`duration`](effecttiming/duration) <span class="badge inline optional">Optional</span>  
The number of milliseconds each iteration of the animation takes to complete. Defaults to 0. Although this is technically optional, keep in mind that your animation will not run if this value is 0.

[`easing`](effecttiming/easing) <span class="badge inline optional">Optional</span>  
The rate of the animation's change over time. Accepts the pre-defined values `"linear"`, `"ease"`, `"ease-in"`, `"ease-out"`, and `"ease-in-out"`, or a custom `"cubic-bezier"` value like `"cubic-bezier(0.42, 0, 0.58, 1)"`. Defaults to `"linear"`.

[`endDelay`](effecttiming/enddelay) <span class="badge inline optional">Optional</span>  
The number of milliseconds to delay after the end of an animation. This is primarily of use when sequencing animations based on the end time of another animation. Defaults to 0.

[`fill`](effecttiming/fill) <span class="badge inline optional">Optional</span>  
Dictates whether the animation's effects should be reflected by the element(s) prior to playing (`"backwards"`), retained after the animation has completed playing (`"forwards"`), or `both`. Defaults to `"none"`.

[`iterationStart`](effecttiming/iterationstart) <span class="badge inline optional">Optional</span>  
Describes at what point in the iteration the animation should start. 0.5 would indicate starting halfway through the first iteration for example, and with this value set, an animation with 2 iterations would end halfway through a third iteration. Defaults to 0.0.

[`iterations`](effecttiming/iterations) <span class="badge inline optional">Optional</span>  
The number of times the animation should repeat. Defaults to `1`, and can also take a value of [`Infinity`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Infinity) to make it repeat for as long as the element exists.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/#the-effecttiming-dictionaries">Web Animations<br />
<span class="small">The definition of 'EffectTiming' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`EffectTiming`

67

52-67

≤79

63

No

Yes

?

67

52-67

67

52-67

63

Yes

?

9.0

6.0-9.0

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

`easing`

52

≤79

63

No

Yes

No

52

52

63

Yes

No

6.0

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

`fill`

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

## See also

- [Web Animations API](web_animations_api)
- [Using the Web Animations API](web_animations_api/using_the_web_animations_api)
- [`Element.animate()`](element/animate)
- [`KeyframeEffect()`](keyframeeffect/keyframeeffect)
- [`KeyframeEffectReadOnly()`](keyframeeffect/keyframeeffect)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EffectTiming</a>
