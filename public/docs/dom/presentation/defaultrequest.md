Presentation.defaultRequest
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

In a [controlling user agent](https://www.w3.org/TR/presentation-api/#dfn-controlling-user-agent), the `defaultRequest` attribute *MUST* return the [default presentation request](https://www.w3.org/TR/presentation-api/#dfn-default-presentation-request) if any, otherwise `null`. In a [receiving browsing context](https://www.w3.org/TR/presentation-api/#dfn-receiving-browsing-context), it *MUST* return `null`.

If set by the [controller](https://www.w3.org/TR/presentation-api/#dfn-controller), the value of the `defaultRequest` attribute *SHOULD* be used by the [controlling user agent](https://www.w3.org/TR/presentation-api/#dfn-controlling-user-agent) as the default presentation request for that [controlling browsing context](https://www.w3.org/TR/presentation-api/#dfn-controlling-browsing-context). If the document object's [active sandboxing flag set](https://www.w3.org/TR/presentation-api/#dfn-active-sandboxing-flag-set) has the [sandboxed presentation browsing context flag](https://www.w3.org/TR/presentation-api/#sandboxed-presentation-browsing-context-flag) set, the [controlling user agent](https://www.w3.org/TR/presentation-api/#dfn-controlling-user-agent) *SHOULD* act as if the default request is not set for that browsing context. When the [controlling user agent](https://www.w3.org/TR/presentation-api/#dfn-controlling-user-agent) wishes to initiate a [`PresentationConnection`](../presentationconnection) on the behalf of that browsing context, it *MUST* [start a presentation](https://www.w3.org/TR/presentation-api/#dfn-start-a-presentation) using the [default presentation request](https://www.w3.org/TR/presentation-api/#dfn-default-presentation-request) for the [controller](https://www.w3.org/TR/presentation-api/#dfn-controller) (as if the controller had called [`defaultRequest.start()`](../presentationrequest/start)).

The [controlling user agent](https://www.w3.org/TR/presentation-api/#dfn-controlling-user-agent) *SHOULD* initiate presentation using the [default presentation request](https://www.w3.org/TR/presentation-api/#dfn-default-presentation-request), only when the user has expressed an intention to do so via a user gesture. For example, by clicking a button in the browser.

**Note:** Some [controlling user agents](https://www.w3.org/TR/presentation-api/#dfn-controlling-user-agent) may allow the user to initiate a default [presentation connection](https://www.w3.org/TR/presentation-api/#dfn-presentation-connection) and select a [presentation display](https://www.w3.org/TR/presentation-api/#dfn-presentation-display) with the same user gesture. For example, the browser chrome could allow the user to pick a display from a menu, or allow the user to tap on an [Near Field Communications (NFC)](https://nfc-forum.org/) enabled display. In this case, when the [controlling user agent](https://www.w3.org/TR/presentation-api/#dfn-controlling-user-agent) asks for permission while [starting a presentation](https://www.w3.org/TR/presentation-api/#dfn-start-a-presentation), the browser could offer that display as the default choice, or consider the gesture as granting permission for the display and bypass display selection entirely.

**Note:** If a [controlling user agent](https://www.w3.org/TR/presentation-api/#dfn-controlling-user-agent) does not support initiation of a [presentation connection](https://www.w3.org/TR/presentation-api/#dfn-presentation-connection) from the browser chrome, setting `defaultRequest` will have no effect.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/presentation-api/#dom-presentation-defaultrequest">Presentation API<br />
<span class="small">The definition of 'defaultRequest' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`defaultRequest`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Presentation/defaultRequest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Presentation/defaultRequest</a>
