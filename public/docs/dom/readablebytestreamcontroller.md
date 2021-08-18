ReadableByteStreamController
============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `ReadableByteStreamController` interface of the [Streams API](streams_api) represents a controller allowing control of a [`ReadableStream`](readablestream)'s state and internal queue. Byte stream controllers are for byte streams.

Constructor
-----------

None. `ReadableByteStreamController` instances are created automatically during `ReadableStream` construction.

Properties
----------

 [`ReadableByteStreamController.byobRequest`](readablebytestreamcontroller/byobrequest) <span class="badge inline readonly">Read only </span>   
Returns the current BYOB pull request.

 [`ReadableByteStreamController.desiredSize`](readablebytestreamcontroller/desiredsize) <span class="badge inline readonly">Read only </span>   
Returns the desired size required to fill the stream's internal queue.

Methods
-------

[`ReadableByteStreamController.close()`](readablebytestreamcontroller/close)  
Closes the associated stream.

[`ReadableByteStreamController.enqueue()`](readablebytestreamcontroller/enqueue)  
Enqueues a given chunk in the associated stream.

[`ReadableByteStreamController.error()`](readablebytestreamcontroller/error)  
Causes any future interactions with the associated stream to error.

Examples
--------

TBD.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://streams.spec.whatwg.org/#rbs-controller-class">Streams<br />
<span class="small">The definition of 'ReadableByteStreamController' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`ReadableByteStreamController`

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

`close`

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

`desiredSize`

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

`enqueue`

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

`error`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ReadableByteStreamController" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ReadableByteStreamController</a>
