TransitionEvent()
=================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `TransitionEvent()` constructor returns a newly created [`TransitionEvent`](../transitionevent), representing an event in relation with an transition.

Syntax
------

    transitionEvent = new TransitionEvent(type, {propertyName: aPropertyName,
                                                 elapsedTime  : aFloat,
                                                 pseudoElement: aPseudoElementName});

### Arguments

*The `TransitionEvent()` constructor also inherits arguments from [`Event()`](../event/event).*

*type*  
Is a [`DOMString`](../domstring) representing the name of the type of the `TransitionEvent`. It is case-sensitive and can only be: `'transitionend'`.

 `propertyName` <span class="badge inline optional">Optional</span>   
Is a [`DOMString`](../domstring) containing the value of the <span class="page-not-created">`property-name`</span> CSS property associated with the transition. It defaults to `""`.

 `elapsedTime` <span class="badge inline optional">Optional</span>   
Is `float` giving the amount of time the animation has been running, in seconds, when this event fired, excluding any time the animation was paused. For an `"animationstart"` event, `elapsedTime` is `0.0` unless there was a negative value for `animation-delay`, in which case the event will be fired with `elapsedTime` containing `(-1 * `*delay*`)`. It defaults to `0.0`.

 `pseudoElement` <span class="badge inline optional">Optional</span>   
Is a [`DOMString`](../domstring), starting with `"::"`, containing the name of the [pseudo-element](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements) the animation runs on. If the animation doesn't run on a pseudo-element but on the element, an empty string: `""``.` It defaults to `""`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions/#dom-transitionevent-transitionevent">CSS Transitions<br />
<span class="small">The definition of 'TransitionEvent()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [Using CSS transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
-   CSS properties: [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition), [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay), [`transition-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration), [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property), [`transition-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent/TransitionEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent/TransitionEvent</a>
