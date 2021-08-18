# PresentationConnectionCloseEvent

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PresentationConnectionCloseEvent` interface of the [Presentation API](presentation_api) is fired on a [`PresentationConnection`](presentationconnection) when it is closed.

## Constructor

<span class="page-not-created">`PresentationConnectionCloseEvent.PresentationConnectionCloseEvent()`</span>  
Creates a new PresentationConnectionCloseEvent.

## Properties

<span class="page-not-created">`PresentationConnectionCloseEvent.message`</span> <span class="badge inline readonly">Read only </span>  
A human-readable message that provides more information about why the connection was closed.

<span class="page-not-created">`PresentationConnectionCloseEvent.reason`</span> <span class="badge inline readonly">Read only </span>  
Indicates why the connection was closed. This property takes one of the following values: `error`, `closed`, or `wentaway`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/presentation-api/#interface-presentationconnectioncloseevent">Presentation API<br />
<span class="small">The definition of 'PresentationConnectionCloseEvent interface' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PresentationConnectionCloseEvent`

50

≤79

51-88

No

Yes

No

No

50

51-79

Yes

No

5.0

`PresentationConnectionCloseEvent`

50

≤79

51-88

No

?

No

No

50

51-79

?

No

5.0

`message`

50

≤79

51-88

No

Yes

No

No

50

51-79

Yes

No

5.0

`reason`

50

≤79

51-88

No

Yes

No

No

50

51-79

Yes

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PresentationConnectionCloseEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PresentationConnectionCloseEvent</a>
