# PresentationRequest.reconnect()

When the `reconnect(presentationId)` method is called on a `PresentationRequest` presentationRequest, the [user agent](https://www.w3.org/TR/presentation-api/#dfn-user-agents) _MUST_ run the following steps to reconnect to a presentation:

Input  
presentationRequest, the [`PresentationRequest`](https://www.w3.org/TR/presentation-api/#idl-def-presentationrequest) object that `reconnect()` was called on.

presentationId, a valid [presentation identifier](https://www.w3.org/TR/presentation-api/#dfn-presentation-identifier)

Output  
P, a [Promise](https://www.w3.org/TR/presentation-api/#dfn-promise)

1.  Using the document's [settings object](https://www.w3.org/TR/presentation-api/#dfn-settings-object) run the [prohibits mixed security contexts algorithm](https://www.w3.org/TR/presentation-api/#dfn-prohibits-mixed-security-contexts-algorithm).
2.  If the result of the algorithm is `"Prohibits Mixed Security Contexts"` and the [presentation request URL](https://www.w3.org/TR/presentation-api/#dfn-presentation-request-urls) of presentationRequest is an [a priori unauthenticated URL](https://www.w3.org/TR/presentation-api/#dfn-a-priori-unauthenticated-url), then return a [Promise](https://www.w3.org/TR/presentation-api/#dfn-promise) rejected with a [`SecurityError`](https://www.w3.org/TR/presentation-api/#dfn-securityerror) and abort these steps.
3.  If the document object's [active sandboxing flag set](https://www.w3.org/TR/presentation-api/#dfn-active-sandboxing-flag-set) has the [sandboxed presentation browsing context flag](https://www.w3.org/TR/presentation-api/#sandboxed-presentation-browsing-context-flag) set, then return a [Promise](https://www.w3.org/TR/presentation-api/#dfn-promise) rejected with a [`SecurityError`](https://www.w3.org/TR/presentation-api/#dfn-securityerror) and abort these steps.
4.  Let P be a new [Promise](https://www.w3.org/TR/presentation-api/#dfn-promise).
5.  Return P but continue running these steps in parallel.
6.  Search the [set of controlled presentations](https://www.w3.org/TR/presentation-api/#dfn-set-of-controlled-presentations) for a [`PresentationConnection`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnection) that meets the following criteria: its [controlling browsing context](https://www.w3.org/TR/presentation-api/#dfn-controlling-browsing-context) is the current [browsing context](https://www.w3.org/TR/presentation-api/#dfn-browsing-context), its [presentation connection state](https://www.w3.org/TR/presentation-api/#dfn-presentation-connection-state) is not [`terminated`](https://www.w3.org/TR/presentation-api/#dom-presentationconnectionstate-terminated), its [presentation URL](https://www.w3.org/TR/presentation-api/#dfn-presentation-url) is equal to one of the [presentation request URLs](https://www.w3.org/TR/presentation-api/#dfn-presentation-request-urls) of presentationRequest and its [presentation identifier](https://www.w3.org/TR/presentation-api/#dfn-presentation-identifier) is equal to presentationId.
7.  If such a [`PresentationConnection`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnection) exists, run the following steps:
    1.  Let S be that [`PresentationConnection`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnection).
    2.  [Resolve](https://www.w3.org/TR/presentation-api/#dfn-resolving-a-promise) P with S.
    3.  If the [presentation connection state](https://www.w3.org/TR/presentation-api/#dfn-presentation-connection-state) of S is [`connecting`](https://www.w3.org/TR/presentation-api/#dom-presentationconnectionstate-connecting) or [`connected`](https://www.w3.org/TR/presentation-api/#dom-presentationconnectionstate-connected), then abort all remaining steps.
    4.  Set the [presentation connection state](https://www.w3.org/TR/presentation-api/#dfn-presentation-connection-state) of S to [`connecting`](https://www.w3.org/TR/presentation-api/#dom-presentationconnectionstate-connecting).
    5.  [Establish a presentation connection](https://www.w3.org/TR/presentation-api/#dfn-establish-a-presentation-connection) with S.
    6.  Abort all remaining steps.
8.  Search the [set of controlled presentations](https://www.w3.org/TR/presentation-api/#dfn-set-of-controlled-presentations) for the first [`PresentationConnection`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnection) that meets the following criteria: its [presentation connection state](https://www.w3.org/TR/presentation-api/#dfn-presentation-connection-state) is not [`terminated`](https://www.w3.org/TR/presentation-api/#dom-presentationconnectionstate-terminated), its [presentation URL](https://www.w3.org/TR/presentation-api/#dfn-presentation-url) is equal to one of the [presentation request URLs](https://www.w3.org/TR/presentation-api/#dfn-presentation-request-urls) of presentationRequest, and its [presentation identifier](https://www.w3.org/TR/presentation-api/#dfn-presentation-identifier) is equal to presentationId.
9.  If such a [`PresentationConnection`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnection) exists, let E be that [`PresentationConnection`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnection), and run the following steps:
    1.  Create a new [`PresentationConnection`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnection) S.
    2.  Set the [presentation identifier](https://www.w3.org/TR/presentation-api/#dfn-presentation-identifier) of S to presentationId.
    3.  Set the [presentation URL](https://www.w3.org/TR/presentation-api/#dfn-presentation-url) of S to the [presentation URL](https://www.w3.org/TR/presentation-api/#dfn-presentation-url) of E.
    4.  Set the [presentation connection state](https://www.w3.org/TR/presentation-api/#dfn-presentation-connection-state) of S to [`connecting`](https://www.w3.org/TR/presentation-api/#dom-presentationconnectionstate-connecting).
    5.  Add S to the [set of controlled presentations](https://www.w3.org/TR/presentation-api/#dfn-set-of-controlled-presentations).
    6.  [Resolve](https://www.w3.org/TR/presentation-api/#dfn-resolving-a-promise) P with S.
    7.  [Queue a task](https://www.w3.org/TR/presentation-api/#dfn-queue-a-task) to [fire](https://www.w3.org/TR/presentation-api/#dfn-firing-an-event) a [trusted event](https://www.w3.org/TR/presentation-api/#dfn-trusted-event) with the name [`connectionavailable`](https://www.w3.org/TR/presentation-api/#dfn-connectionavailable), that uses the [`PresentationConnectionAvailableEvent`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnectionavailableevent) interface with the [`connection`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnectionavailableevent-connection) attribute initialized to S, at presentationRequest. The event must not bubble and cancelable and should have no default action.
    8.  [Establish a presentation connection](https://www.w3.org/TR/presentation-api/#dfn-establish-a-presentation-connection) with S.
    9.  Abort all remaining steps.
10. [Reject](https://www.w3.org/TR/presentation-api/#dfn-rejecting-a-promise) P with a [`NotFoundError`](https://www.w3.org/TR/presentation-api/#dfn-notfounderror) exception.

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

`reconnect`

48

≤79

51-88

No

35

No

No

48

51-79

35

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PresentationRequest/reconnect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PresentationRequest/reconnect</a>
