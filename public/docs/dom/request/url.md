# Request.url

The `url` read-only property of the [`Request`](../request) interface contains the URL of the request.

## Syntax

    var myURL = request.url;

### Value

A [`USVString`](../usvstring) indicating the url of the request.

## Example

In the following snippet, we create a new request using the [`Request.Request()`](request) constructor (for an image file in the same directory as the script), then save the url of the request in a variable:

    var myRequest = new Request('flowers.jpg');
    var myURL = myRequest.url; // "https://mdn.github.io/fetch-examples/fetch-request/flowers.jpg"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-request-url">Fetch<br />
<span class="small">The definition of 'url' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

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

`url`

42

Fragment support added in Chrome 59.

14

39

34

No

29

Fragment support added in Opera 46.

10.1

42

Fragment support added in Chrome 59.

42

Fragment support added in Chrome 59.

39

29

Fragment support added in Opera 46.

10.3

4.0

Fragment support added in Samsung Internet 7.0.

## See also

- [ServiceWorker API](../service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Request/url" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Request/url</a>
