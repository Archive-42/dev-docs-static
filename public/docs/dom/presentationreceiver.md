# PresentationReceiver

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `PresentationReceiver` interface of the [Presentation API](presentation_api) provides a means for a receiving browsing context to access controlling browsing contexts and communicate with them.

## Properties

<span class="page-not-created">`PresentationReceiver.connectionList`</span> <span class="badge inline readonly">Read only </span>  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`PresentationConnectionList`](presentationconnectionlist) object containing a list of incoming presentation connections.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/presentation-api/#interface-presentationreceiver">Presentation API<br />
<span class="small">The definition of 'PresentationReceiver' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PresentationReceiver`

55

≤79

51-88

No

Yes

No

No

55

51-79

Yes

No

6.0

`connectionList`

55

≤79

51-88

No

Yes

No

No

55

51-79

Yes

No

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PresentationReceiver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PresentationReceiver</a>
