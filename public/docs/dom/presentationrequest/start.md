PresentationRequest.start()
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `start()` property of the [`PresentationRequest`](../presentationrequest) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`PresentationConnection`](../presentationconnection) after the user agent prompts the user to select a display and grant permission to use that display.

Syntax
------

    var promise = presentationRequest.start()
    promise.then(function(PresentationConnection) { ... })
           .catch(function(error) { ...})

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with a [`PresentationConnection`](../presentationconnection).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/presentation-api/#dom-presentationrequest-start">Presentation API<br />
<span class="small">The definition of 'start()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PresentationRequest/start" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PresentationRequest/start</a>
