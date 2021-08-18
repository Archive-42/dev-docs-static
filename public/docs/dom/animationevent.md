# AnimationEvent

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `AnimationEvent` interface represents events providing information related to [animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations).

## Constructor

[`AnimationEvent()`](animationevent/animationevent)  
Creates an `AnimationEvent` event with the given parameters.

## Properties

_Also inherits properties from its parent [`Event`](event)_.

[`AnimationEvent.animationName`](animationevent/animationname) <span class="badge inline readonly">Read only </span>  
Is a [`DOMString`](domstring) containing the value of the [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name) that generated the animation.

[`AnimationEvent.elapsedTime`](animationevent/elapsedtime) <span class="badge inline readonly">Read only </span>  
Is a `float` giving the amount of time the animation has been running, in seconds, when this event fired, excluding any time the animation was paused. For an `animationstart` event, `elapsedTime` is `0.0` unless there was a negative value for [`animation-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay), in which case the event will be fired with `elapsedTime` containing `(-1 * delay)`.

[`AnimationEvent.pseudoElement`](animationevent/pseudoelement) <span class="badge inline readonly">Read only </span>  
Is a [`DOMString`](domstring), starting with `'::'`, containing the name of the [pseudo-element](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) the animation runs on. If the animation doesn't run on a pseudo-element but on the element, an empty string: `''`.

## Methods

_Also inherits methods from its parent [`Event`](event)_.

[`AnimationEvent.initAnimationEvent()`](animationevent/initanimationevent) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Initializes a `AnimationEvent` created using the deprecated [`Document.createEvent("AnimationEvent")`](document/createevent) method.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#interface-animationevent">CSS Animations Level 1<br />
<span class="small">The definition of 'AnimationEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

1-70

12

6

10

30

15-57

12.1-15

12-15

9.1

4

43

1-70

43

18-70

6

30

14-49

12.1-14

12-14

9.3

3.2

4.0

1.0-10.0

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

`animationName`

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

`pseudoElement`

68

79

23

No

No

No

68

68

23

No

No

10.0

## See also

- [Using CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
- Animation-related CSS properties and at-rules: [`animation`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation), [`animation-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay), [`animation-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-direction), [`animation-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration), [`animation-fill-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode), [`animation-iteration-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count), [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name), [`animation-play-state`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state), [`animation-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function), [`@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent</a>
