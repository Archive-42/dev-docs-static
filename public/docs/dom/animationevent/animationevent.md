# AnimationEvent()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `AnimationEvent()` constructor returns a newly created [`AnimationEvent`](../animationevent), representing an event in relation with an animation.

## Syntax

    animationEvent = new AnimationEvent(type, {animationName: aPropertyName,
                                               elapsedTime  : aFloat,
                                               pseudoElement: aPseudoElementName});

### Parameters

_The `AnimationEvent()` constructor also inherits arguments from [`Event()`](../event/event)._

`type`  
A [`DOMString`](../domstring) representing the name of the type of the `AnimationEvent`. It is case-sensitive and can be: `'animationstart'`, `'animationend'`, or `'animationiteration'`.

`animationName` <span class="badge inline optional">Optional</span>  
A [`DOMString`](../domstring) containing the value of the [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name) CSS property associated with the transition. It defaults to `""`.

`elapsedTime` <span class="badge inline optional">Optional</span>  
A `float` giving the amount of time the animation has been running, in seconds, when this event fired, excluding any time the animation was paused. For an `"animationstart"` event, `elapsedTime` is `0.0` unless there was a negative value for [`animation-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay), in which case the event will be fired with `elapsedTime` containing `(-1 * `_delay_`)`. It defaults to `0.0`.

`pseudoElement` <span class="badge inline optional">Optional</span>  
Is a [`DOMString`](../domstring), starting with `"::"`, containing the name of the [pseudo-element](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) the animation runs on. If the animation doesn't run on a pseudo-element but on the element itself, specify an empty string: `""`. It defaults to `""`.

### Return value

A new [`AnimationEvent`](../animationevent), initialized per any provided options.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#dom-animationevent-animationevent">CSS Animations Level 1<br />
<span class="small">The definition of 'AnimationEvent()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`AnimationEvent`

43

14

23

No

No

No

43

43

23

No

?

4.0

## See also

- [Using CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
- Animation-related CSS properties and at-rules: [`animation`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation), [`animation-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay), [`animation-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-direction), [`animation-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration), [`animation-fill-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode), [`animation-iteration-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count), [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name), [`animation-play-state`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state), [`animation-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function), [`@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes)
- The [`AnimationEvent`](../animationevent) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent/AnimationEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent/AnimationEvent</a>
