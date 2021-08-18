TransitionEvent.pseudoElement
=============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `TransitionEvent.pseudoElement` read-only property is a [`DOMString`](../domstring), starting with `'::'`, containing the name of the [pseudo-element](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) the animation runs on. If the transition doesn't run on a pseudo-element but on the element, an empty string: `''``.`

Syntax
------

    name = TransitionEvent.pseudoElement

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions/#Events-TransitionEvent-pseudoElement">CSS Transitions<br />
<span class="small">The definition of 'TransitionEvent.pseudoElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`pseudoElement`

2

79

23

No

Yes

6

≤37

18

23

Yes

No

1.0

See also
--------

-   [Using CSS transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
-   [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition), [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay), [`transition-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration), [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property), [`transition-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent/pseudoElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent/pseudoElement</a>
