XMLHttpRequest.multipart
========================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Obsolete since Gecko 22

**This Gecko-only feature was removed in Firefox/Gecko 22.** Please use [Server-Sent Events](../server-sent_events), [Web Sockets](../websockets_api), or `responseText` from progress events instead.

This boolean indicates if the response is expected to be a stream of possibly multiple XML documents. If set to `true`, the content type of the initial response must be `multipart/x-mixed-replace` or an error will occur. All requests must be asynchronous.

This enables support for server push; for each XML document that's written to this request, a new XML DOM document is created and the `onload` handler is called between documents.

**Note:** When this is set, the `onload` handler and other event handlers are not reset after the first XMLdocument is loaded, and the `onload` handler is called after each part of the response is received.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/multipart" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/multipart</a>
