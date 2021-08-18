# PresentationRequest

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

A `PresentationRequest` object is used to initiate or reconnect to a presentation made by a [controlling browsing context](https://www.w3.org/TR/presentation-api/#dfn-controlling-browsing-context). The `PresentationRequest` object _MUST_ be implemented in a [controlling browsing context](https://www.w3.org/TR/presentation-api/#dfn-controlling-browsing-context) provided by a [controlling user agent](https://www.w3.org/TR/presentation-api/#dfn-controlling-user-agent).

When a `PresentationRequest` is constructed, the given `urls` _MUST_ be used as the list of presentation request URLs which are each a possible [presentation URL](https://www.w3.org/TR/presentation-api/#dfn-presentation-url) for the `PresentationRequest` instance.

## Constructor

[`PresentationRequest()`](presentationrequest/presentationrequest)  
Creates a `PresentationRequest`.

## Properties

None

### Event handlers

[`PresentationRequest.onconnectionavailable`](presentationrequest/onconnectionavailable)  
Fires on a successful call to [`PresentationRequest.start()`](presentationrequest/start) or <span class="page-not-created">`PresentationRequest.join()`</span>. This method provides a object with a reference to the created or joined object.

## Methods

[`PresentationRequest.start()`](presentationrequest/start)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`PresentationConnection`](presentationconnection) after the user agent prompts the user to select a display and grant permission to use that display.

[`PresentationRequest.reconnect()`](presentationrequest/reconnect)  
When the `reconnect(presentationId)` method is called on a `PresentationRequest` presentationRequest, the [user agent](https://www.w3.org/TR/presentation-api/#dfn-user-agents) _MUST_ run the following steps to reconnect to a presentation.

[`PresentationRequest.getAvailability()`](presentationrequest/getavailability)  
When the `getAvailability()` method is called, the user agent _MUST_ run the steps as the link.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/presentation-api/#interface-presentationrequest">Presentation API<br />
<span class="small">The definition of 'PresentationRequest interface' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PresentationRequest`

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

`PresentationRequest`

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

`getAvailability`

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

`onconnectionavailable`

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

`secure_context_required`

61

≤79

Yes-61

No

48

No

No

61

Yes-79

45

No

8.0

`start`

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

`startWithDevice`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PresentationRequest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PresentationRequest</a>
