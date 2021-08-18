PresentationConnectionList
==========================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

`PresentationConnectionList` is the collection of incoming presentation connections.

Properties
----------

 <span class="page-not-created">`PresentationConnectionList.connections`</span> <span class="badge inline readonly">Read only </span>   
Returns the non-terminated set of [`PresentationConnection`](presentationconnection)s in the [set of presentation controllers](https://www.w3.org/TR/presentation-api/#dfn-set-of-presentation-controllers).

### Event Handlers

<span class="page-not-created">`PresentationConnectionList.onconnectionavailable`</span>  
Fired whenever a new [presentation connection](https://www.w3.org/TR/presentation-api/#dfn-presentation-connection) becomes available.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/presentation-api/#interface-presentationconnectionlist">Presentation API<br />
<span class="small">The definition of 'PresentationConnectionList' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PresentationConnectionList`

51

≤79

51-88

No

Yes

No

No

51

51-79

Yes

No

5.0

`connections`

51

≤79

51-88

No

Yes

No

No

51

51-79

Yes

No

5.0

`onconnectionavailable`

51

≤79

51-88

No

Yes

No

No

51

51-79

Yes

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PresentationConnectionList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PresentationConnectionList</a>
