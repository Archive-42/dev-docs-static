# AnimationEvent.initAnimationEvent()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

## Summary

The `AnimationEvent.initAnimationEvent()` method Initializes an animation event created using the deprecated [`Document.createEvent("AnimationEvent")`](../document/createevent) method.

`AnimationEvent` created this way are untrusted.

**Note:** During the standardization process, this method was removed from the specification. It has been deprecated and is in the progress of being removed from most implementations. **Do not use this method**; instead, use the standard constructor, [`AnimationEvent()`](animationevent), to create a synthetic [`AnimationEvent`](../animationevent).

## Syntax

    animationEvent.initAnimationEvent(typeArg, canBubbleArg, cancelableArg, animationNameArg, elapsedTimeArg);

### Parameters

`typeArg`  
A [`DOMString`](../domstring) identifying the specific type of animation event that occurred. The following values are allowed:

<table><thead><tr class="header"><th>Value</th><th>Meaning</th></tr></thead><tbody><tr class="odd"><td><code>animationstart</code></td><td>The animation has started.</td></tr><tr class="even"><td><code>animationend</code></td><td>The animation completed.</td></tr><tr class="odd"><td><code>animationiteration</code></td><td>The current iteration just completed.</td></tr></tbody></table>

`canBubbleArg`  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating if the event can bubble (`true`) or not (`false)`.

`cancelableArg`  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating if the event associated action can be avoided (`true`) or not (`false)`.

`animationNameArg`  
A [`DOMString`](../domstring) containing the value of the [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name) CSS property associated with the transition.

`elapsedTimeArg`  
A `float` indicating the amount of time the animation has been running, in seconds, as of the time the event was fired, excluding any time the animation was paused. For an `"animationstart"` event, `elapsedTime` is `0.0` unless there was a negative value for `animation-delay`, in which case the event will be fired with `elapsedTime` containing `(-1 * `_delay_`)`.

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

`initAnimationEvent`

1-18

12-16

6-23

10

12.1-15

4-6

No

No

6-23

12.1-14

3.2-6

No

## See also

- [Using CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
- Animation-related CSS properties and at-rules: [`animation`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation), [`animation-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay), [`animation-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-direction), [`animation-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration), [`animation-fill-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode), [`animation-iteration-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count), [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name), [`animation-play-state`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state), [`animation-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function), [`@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes).
- The [`AnimationEvent`](../animationevent) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent/initAnimationEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent/initAnimationEvent</a>
