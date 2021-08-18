# AnimationEvent.pseudoElement

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

## Summary

The `AnimationEvent.pseudoElement` read-only property is a [`DOMString`](../domstring), starting with `'::'`, containing the name of the [pseudo-element](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) the animation runs on. If the animation doesn't run on a pseudo-element but on the element, an empty string: ` ''``. `

## Syntax

    name = AnimationEvent.pseudoElement

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#dom-animationevent-pseudoelement">CSS Animations Level 1<br />
<span class="small">The definition of 'AnimationEvent.pseudoElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

- [Chromium Issue 437132](https://bugs.chromium.org/p/chromium/issues/detail?id=437132)
- [Using CSS animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
- Animation-related CSS properties and at-rules: [`animation`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation), [`animation-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay), [`animation-direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-direction), [`animation-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration), [`animation-fill-mode`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode), [`animation-iteration-count`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count), [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name), [`animation-play-state`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state), [`animation-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function), [`@keyframes`](https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes).
- The [`AnimationEvent`](../animationevent) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent/pseudoElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent/pseudoElement</a>
