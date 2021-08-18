RequestDestination
==================

The `RequestDestination` enumerated type contains the permitted values for a request's [`destination`](request/destination). These string values indicate potential types of content that a request may try to retrieve.

Values
------

`""`  
The default value of `destination` is used for destinations that do not have their own value. [navigator.sendBeacon()](navigator/sendbeacon), [EventSource](eventsource), [&lt;a ping&gt;](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a#attr-ping), [&lt;area ping&gt;](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area#attr-ping), [fetch()](windoworworkerglobalscope/fetch), [XMLHttpRequest](xmlhttprequest), [WebSocket](websocket), [Cache](cache) and more.

`"audio"`  
The target is audio data.

`"audioworklet"`  
The target is data being fetched for use by an audio worklet.

`"document"`  
The target is a document (HTML or XML).

`"embed"`  
The target is embedded content.

`"font"`  
The target is a font.

`"image"`  
The target is an image.

`"manifest"`  
The target is a manifest.

`"object"`  
The target is an object.

`"paintworklet"`  
The target is a paint worklet.

`"report"`  
The target is a report.

`"script"`  
The target is a script.

`"serviceworker"`  
The target is a service worker.

`"sharedworker"`  
The target is a shared worker.

`"style"`  
The target is a style

`"track"`  
The target is an HTML [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track).

`"video"`  
The target is video data.

`"worker"`  
The target is a worker.

`"xslt"`  
The target is an XLST transform.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#requestdestination">Fetch<br />
<span class="small">The definition of 'RequestDestination' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`RequestDestination`

65

14

61

?

52

?

65

65

61

47

?

9.0

See also
--------

-   [Fetch API](fetch_api)
-   [Using Fetch](fetch_api/using_fetch)
-   [`Request.destination`](request/destination)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RequestDestination" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RequestDestination</a>
