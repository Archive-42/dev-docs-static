PresentationConnectionAvailableEvent
====================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PresentationConnectionAvailableEvent` interface of the [Presentation API](presentation_api) is fired on a [`PresentationRequest`](presentationrequest) when a connection associated with the object is created.

A [controlling user agent](https://www.w3.org/TR/presentation-api/#dfn-controlling-user-agent) [fires](https://www.w3.org/TR/presentation-api/#dfn-firing-an-event) a [trusted event](https://www.w3.org/TR/presentation-api/#dfn-trusted-event) named [`connectionavailable`](https://www.w3.org/TR/presentation-api/#dfn-connectionavailable) on a [`PresentationRequest`](https://www.w3.org/TR/presentation-api/#idl-def-presentationrequest) when a connection associated with the object is created. It is fired at the [`PresentationRequest`](https://www.w3.org/TR/presentation-api/#idl-def-presentationrequest) instance, using the [`PresentationConnectionAvailableEvent`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnectionavailableevent) interface, with the [`connection`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnectionavailableevent-connection) attribute set to the [`PresentationConnection`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnection) object that was created. The event is fired for each connection that is created for the [controller](https://www.w3.org/TR/presentation-api/#dfn-controller), either by the [controller](https://www.w3.org/TR/presentation-api/#dfn-controller) calling `start()` or `reconnect()`, or by the [controlling user agent](https://www.w3.org/TR/presentation-api/#dfn-controlling-user-agent) creating a connection on the controller's behalf via [`defaultRequest`](https://www.w3.org/TR/presentation-api/#dom-presentation-defaultrequest).

Constructor
-----------

[`PresentationConnectionAvailableEvent()`](presentationconnectionavailableevent/presentationconnectionavailableevent)  
Creates a new PresentationConnectionAvailableEvent.

Properties
----------

 [`PresentationConnectionAvailableEvent.connection`](presentationconnectionavailableevent/connection) <span class="badge inline readonly">Read only </span>   
Returns a references to the [`PresentationConnection`](presentationconnection) object that fired the event.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/presentation-api/#interface-presentationconnectionavailableevent">Presentation API<br />
<span class="small">The definition of 'PresentationConnectionAvailableEvent interface' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PresentationConnectionAvailableEvent`

48

≤79

51-88

No

Yes

No

No

48

51-79

Yes

No

5.0

`PresentationConnectionAvailableEvent`

48

≤79

51-88

No

?

No

No

48

51-79

?

No

5.0

`connection`

48

≤79

51-88

No

Yes

No

No

48

51-79

Yes

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PresentationConnectionAvailableEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PresentationConnectionAvailableEvent</a>
