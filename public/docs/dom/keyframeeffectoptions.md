# KeyframeEffectOptions

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `KeyframeEffectOptions` dictionary, part of the [Web Animations API](web_animations_api), is used by [`Element.animate()`](element/animate) and [`KeyframeEffect()`](keyframeeffect/keyframeeffect) to describe timing properties for animation effects. These properties are all optional, although without setting a `duration` the animation will not play.

In other words, these properties describe how the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) should go about making the transition from keyframe to keyframe, and how to behave when the animation begins and ends.

## Properties

`composite` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="badge inline optional">Optional</span>  
Determines how values are combined between this animation and other, separate animations that do not specify their own specific composite operation. Defaults to `replace`.

- `add` dictates an additive effect, where each successive iteration builds on the last. For instance with `transform`, a `translateX(-200px)` would not override an earlier `rotate(20deg)` value but result in `translateX(-200px) rotate(20deg)`.
- `accumulate` is similar but a little smarter: `blur(2)` and `blur(5)` become `blur(7)`, not `blur(2) blur(5)`.
- `replace` overwrites the previous value with the new one.

`iterationComposite` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="badge inline optional">Optional</span>  
Determines how values build from iteration to iteration in this animation. Can be set to `accumulate` or `replace` (see above). Defaults to `replace`.

`pseudoElement` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="badge inline optional">Optional</span>  
The selector of the pseudo-element to be targeted, if any. Defaults to `null`.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-2/#the-keyframeeffectoptions-dictionary">Web Animations Level 2<br />
<span class="small">The definition of 'KeyframeEffectOptions' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Added the <code>iterationComposite</code> option.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/web-animations-1/#the-keyframeeffectoptions-dictionary">Web Animations<br />
<span class="small">The definition of 'KeyframeEffectOptions' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.KeyframeEffectOptions`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [`EffectTiming`](effecttiming)
- [Web Animations API](web_animations_api)
- [Using the Web Animations API](web_animations_api/using_the_web_animations_api)
- [`Element.animate()`](element/animate)
- [`KeyframeEffect()`](keyframeeffect/keyframeeffect)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffectOptions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KeyframeEffectOptions</a>
