PresentationConnection
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PresentationConnection` interface of the [Presentation API](presentation_api) provides methods and properties for managing a single presentation. Each [presentation connection](https://www.w3.org/TR/presentation-api/#dfn-presentation-connection) is represented by a `PresentationConnection` object. Both the [controlling user agent](https://www.w3.org/TR/presentation-api/#dfn-controlling-user-agent) and [receiving user agent](https://www.w3.org/TR/presentation-api/#dfn-receiving-user-agent) *MUST* implement `PresentationConnection`.

Properties
----------

[`PresentationConnection.binaryType`](presentationconnection/binarytype)  
Returns either blob or arrayBuffer. When a `PresentationConnection` object is created, its [`binaryType`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnection-binarytype) IDL attribute *MUST* be set to the string " [`arraybuffer`](https://www.w3.org/TR/presentation-api/#dom-binarytype-arraybuffer)".

 [`PresentationConnection.id`](presentationconnection/id) <span class="badge inline readonly">Read only </span>   
Provides the presentation connection identifier.

 [`PresentationConnection.state`](presentationconnection/state) <span class="badge inline readonly">Read only </span>   
Returns the [presentation connection](https://www.w3.org/TR/presentation-api/#dfn-presentation-connection)'s current state.

 [`PresentationConnection.url`](presentationconnection/url) <span class="badge inline readonly">Read only </span>   
Returns the URL used to create or reconnect to the presentation.

### Event handlers

<span class="page-not-created">`PresentationConnection.onclose`</span>  
Fired when there is a call to [`PresentationConnection.close()`](presentationconnection/close).

<span class="page-not-created">`PresentationConnection.onconnect`</span>  
Fired when a presentation connection is established.

<span class="page-not-created">`PresentationConnection.onmessage`</span>  
Fired when there is a call to [`PresentationConnection.send()`](presentationconnection/send).

<span class="page-not-created">`PresentationConnection.onterminated`</span>  
Fired when there is a call to [`PresentationConnection.terminate()`](presentationconnection/terminate).

Methods
-------

[`PresentationConnection.close()`](presentationconnection/close)  
Closes the current connection and sends a [`PresentationConnectionCloseEvent`](presentationconnectioncloseevent) to <span class="page-not-created">`PresentationConnection.onclosed`</span>.

[`PresentationConnection.send()`](presentationconnection/send)  
Sends either binary or text data between a controlling browsing context and a presenting browsing context.

[`PresentationConnection.terminate()`](presentationconnection/terminate)  
Terminates the current connection and fires <span class="page-not-created">`PresentationConnection.onterminated`</span>.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/presentation-api/#interface-presentationconnection">Presentation API<br />
<span class="small">The definition of 'PresentationConnection interface' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PresentationConnection`

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

`binaryType`

Yes

≤79

51-88

No

Yes

No

No

Yes

51-79

Yes

No

Yes

`close`

49

≤79

51-88

No

Yes

No

No

49

51-79

Yes

No

5.0

`id`

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

`onclose`

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

`onconnect`

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

`onmessage`

Yes

≤79

51-88

No

Yes

No

No

Yes

51-79

Yes

No

Yes

`onterminate`

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

`send`

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

`state`

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

`terminate`

Yes

≤79

51-88

No

Yes

No

No

Yes

51-79

Yes

No

Yes

`url`

57

≤79

51-88

No

Yes

No

No

57

51-79

Yes

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PresentationConnection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PresentationConnection</a>
