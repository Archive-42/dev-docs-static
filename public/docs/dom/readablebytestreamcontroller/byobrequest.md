ReadableByteStreamController.byobRequest
========================================

**Draft**

This page is not complete.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `byobRequest` read-only property of the [`ReadableByteStreamController`](../readablebytestreamcontroller) interface returns the current BYOB pull request, or `undefined` if there are no pending requests.

Syntax
------

    var request = readableByteStreamController.byobRequest;

### Value

A [`ReadableStreamBYOBRequest`](../readablestreambyobrequest) object instance, or `undefined`.

Examples
--------

TBD.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#rbs-controller-byob-request">Streams<br />
<span class="small">The definition of 'byobRequest' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`byobRequest`

89

89

No

No

75

No

89

89

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableByteStreamController/byobRequest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableByteStreamController/byobRequest</a>
