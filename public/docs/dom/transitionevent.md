TransitionEvent
===============

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `TransitionEvent` interface represents events providing information related to [transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions).

Constructor
-----------

[`TransitionEvent()`](transitionevent/transitionevent)  
Creates a `TransitionEvent` event with the given parameters.

Properties
----------

*Also inherits properties from its parent [`Event`](event)*.

 <span class="page-not-created">`TransitionEvent.propertyName`</span> <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring) containing the name CSS property associated with the transition.

 [`TransitionEvent.elapsedTime`](transitionevent/elapsedtime) <span class="badge inline readonly">Read only </span>   
Is a `float` giving the amount of time the transition has been running, in seconds, when this event fired. This value is not affected by the [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay) property.

 [`TransitionEvent.pseudoElement`](transitionevent/pseudoelement) <span class="badge inline readonly">Read only </span>   
Is a [`DOMString`](domstring), starting with `::`, containing the name of the [pseudo-element](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) the animation runs on. If the transition doesn't run on a pseudo-element but on the element, an empty string: `''`.

Types of `TransitionEvent`
--------------------------

[`transitioncancel`](htmlelement/transitioncancel_event)  
An [`Event`](event) fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions) has been cancelled.

[`transitionend`](htmlelement/transitionend_event)  
An [`Event`](event) fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions) has finished playing.

[`transitionrun`](htmlelement/transitionrun_event)  
An [`Event`](event) fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions) is created, when it is added to a set of running transitions, though not nessarilty started

[`transitionstart`](htmlelement/transitionstart_event)  
An [`Event`](event) fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions) has started transitioning.

Methods
-------

*Also inherits properties from its parent [`Event`](event)*.

 [`TransitionEvent.initTransitionEvent()`](transitionevent/inittransitionevent) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Initializes a `TransitionEvent` created using the deprecated [`Document.createEvent("TransitionEvent")`](document/createevent) method.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions/#interface-transitionevent">CSS Transitions<br />
<span class="small">The definition of 'TransitionEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`TransitionEvent`

27

2-71

12

4

10

Yes

Yes

≤37

≤37-71

27

18-71

4

Yes

Yes

2.0

1.0-10.0

`TransitionEvent`

27

79

23

No

Yes

No

≤37

27

23

Yes

No

2.0

`animationName`

No

12-79

4

10

Yes

Yes

No

No

4

Yes

Yes

No

`elapsedTime`

2

12

4

10

Yes

6

≤37

18

4

Yes

Yes

1.0

`initTransitionEvent`

No

Removal version unknown.

12-79

6-23

10

No

Removal version unknown.

Yes

No

Removal version unknown.

No

Removal version unknown.

6-23

No

Removal version unknown.

Yes

No

Removal version unknown.

`propertyName`

2

12

Yes

?

Yes

6

≤37

18

Yes

Yes

Yes

1.0

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
-   CSS properties: [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition), [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay), [`transition-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration), [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property), [`transition-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent</a>
