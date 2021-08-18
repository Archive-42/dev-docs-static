TransitionEvent.initTransitionEvent()
=====================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `TransitionEvent.initTransitionEvent()` method Initializes a transition event created using the deprecated [`Document.createEvent("TransitionEvent")`](../document/createevent) method.

`TransitionEvent` created that way are untrusted.

**Note:** this method has been dropped during the standard process. It has been deprecated and is in the progress of been removed from most implementation. Do not use it anymore, use the standard constructor, [`TransitionEvent()`](transitionevent), to create a synthetic [`TransitionEvent`](../transitionevent)

Syntax
------

    transitionEvent.initTransitionEvent(typeArg, canBubbleArg, cancelableArg, transitionNameArg, elapsedTimeArg);

### Parameters

*typeArg*  
Is a [`DOMString`](../domstring) identifying the specific type of transition event that occurred. The following value is allowed:

<table><thead><tr class="header"><th>Value</th><th>Meaning</th></tr></thead><tbody><tr class="odd"><td><code>transitionend</code></td><td>The transition completed.</td></tr></tbody></table>

*canBubbleArg*  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating if the event can bubble (`true`) or not (`false)`.

*cancelableArg*  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating if the event associated action can be avoided (`true`) or not (`false)`.

*transitionNameArg*  
Is a [`DOMString`](../domstring) containing the name of the CSS property associated with the transition. This value is not affected by the [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay) property.

*elapsedTimeArg*  
Is `float` giving the amount of time the transition has been running, in seconds, when this event fired.

Specifications
--------------

*This method is non-standard and not part of any specification, though it was present in early drafts of [CSS Transitions](https://drafts.csswg.org/css-transitions/).*

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

See also
--------

-   [Using CSS transitions](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions)
-   CSS properties: [`transition`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition), [`transition-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay), [`transition-duration`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration), [`transition-property`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property), [`transition-timing-function`](https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent/initTransitionEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent/initTransitionEvent</a>
