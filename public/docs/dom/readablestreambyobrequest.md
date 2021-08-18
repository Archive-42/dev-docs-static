ReadableStreamBYOBRequest
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `ReadableStreamBYOBRequest` interface of the [Streams API](streams_api) represents a pull request into a [`ReadableByteStreamController`](readablebytestreamcontroller) view.

A view, as mentioned below, refers to a typed array representing the destination region to which the associated `ReadableByteStreamController` controller can write generated data.

Constructor
-----------

None. `ReadableStreamBYOBRequest` instance is created automatically by `ReadableByteStreamController` as needed.

Properties
----------

 [`ReadableStreamBYOBRequest.view`](readablestreambyobrequest/view) <span class="badge inline readonly">Read only </span>   
Returns the current view.

Methods
-------

[`ReadableStreamBYOBRequest.respond()`](readablestreambyobrequest/respond)  
xxx

[`ReadableStreamBYOBRequest.respondWithNewView()`](readablestreambyobrequest/respondwithnewview)  
xxx

Examples
--------

TBD.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#rs-byob-request-class">Streams<br />
<span class="small">The definition of 'ReadableStreamBYOBRequest' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`ReadableStreamBYOBRequest`

No

No

No

No

No

No

No

No

No

No

No

No

`respond`

No

No

No

No

No

No

No

No

No

No

No

No

`respondWithNewView`

No

No

No

No

No

No

No

No

No

No

No

No

`view`

No

No

No

No

No

No

No

No

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamBYOBRequest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableStreamBYOBRequest</a>
