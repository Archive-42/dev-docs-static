PresentationConnectionAvailableEvent.connection
===============================================

When an incoming connection is created, a [receiving user agent](https://www.w3.org/TR/presentation-api/#dfn-receiving-user-agent) [fires](https://www.w3.org/TR/presentation-api/#dfn-firing-an-event) a [trusted event](https://www.w3.org/TR/presentation-api/#dfn-trusted-event), named [`connectionavailable`](https://www.w3.org/TR/presentation-api/#dfn-connectionavailable), on a [`PresentationReceiver`](https://www.w3.org/TR/presentation-api/#idl-def-presentationreceiver). The [trusted event](https://www.w3.org/TR/presentation-api/#dfn-trusted-event) is fired at the [presentation controller's monitor](https://www.w3.org/TR/presentation-api/#dfn-presentation-controllers-monitor), using the [`PresentationConnectionAvailableEvent`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnectionavailableevent) interface, with the [`connection`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnectionavailableevent-connection) attribute set to the [`PresentationConnection`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnection) object that was created.

The event is fired for all connections that are created when [monitoring incoming presentation connections](https://www.w3.org/TR/presentation-api/#dfn-monitoring-incoming-presentation-connections).

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PresentationConnectionAvailableEvent/connection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PresentationConnectionAvailableEvent/connection</a>
