# AnimationEvent.elapsedTime

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `AnimationEvent.elapsedTime` read-only property is a `float` giving the amount of time the animation has been running, in seconds, when this event fired, excluding any time the animation was paused. For an [`animationstart`](../htmlelement/animationstart_event) event, `elapsedTime` is `0.0` unless there was a negative value for [`animation-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay), in which case the event will be fired with `elapsedTime` containing `(-1 * `_delay_`)`.

## Syntax

    time = AnimationEvent.elapsedTime

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#dom-animationevent-elapsedtime">CSS Animations Level 1<br />
<span class="small">The definition of 'AnimationEvent.elapsedTime' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`elapsedTime`

43

12

6

10

30

9

43

43

6

30

9

4.0

## See also

- [Using CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
- Animation-related CSS properties and at-rules: [`animation`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation), [`animation-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay), [`animation-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-direction), [`animation-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration), [`animation-fill-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode), [`animation-iteration-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count), [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name), [`animation-play-state`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state), [`animation-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function), [`@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes).
- The [`AnimationEvent`](../animationevent) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent/elapsedTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent/elapsedTime</a>
