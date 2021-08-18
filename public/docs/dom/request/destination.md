Request.destination
===================

The `destination` read-only property of the **[`Request`](../request)** interface returns a string describing the type of content being requested. The string must be one of those found in the [`RequestDestination`](../requestdestination) enumerated type or the empty string, which is the default value.

The `destination` is used by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) to, for example, help determine which set of rules to follow for CORS purposes, or how to navigate any complicated code paths that affect how specific types of request get handled.

These destinations vary substantially in how they operate. Some are data receptacles, where the received data is stored for processing later. Others are script-based, in which case the received data is delivered to a script by calling it and passing the data along. Script-based destinations include [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) elements, as well as any of the [`Worklet`](../worklet)-based destinations (including [`AudioWorklet`](../audioworklet) and [`PaintWorklet`](../paintworklet)), and the [`Worker`](../worker)-based destinations, including [`ServiceWorker`](../serviceworker) and [`SharedWorker`](../sharedworker).

Syntax
------

    var destination = request.destination;

### Value

A string from the [`RequestDestination`](../requestdestination) enumerated type which indicates the type of content the request is asking for. This type is much broader than the usual document type values (such as `"document"` or `"manifest"`), and may include contextual cues such as `"image"` or `"worker"` or `"audioworklet"`.

Example
-------

In the following snippet, we create a new request using the [`Request()`](request) constructor (for an image file in the same directory as the script), then save the request's destination:

    var myRequest = new Request('flowers.jpg');
    var myDestination = myRequest.destination; // returns the empty string by default

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-request-destination">Fetch<br />
<span class="small">The definition of 'destination' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`destination`

65

14

61

No

52

10.1

65

65

61

47

10.3

9.0

See also
--------

-   [ServiceWorker API](../service_worker_api)
-   [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Request/destination" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Request/destination</a>
