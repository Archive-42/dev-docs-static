# Request.referrerPolicy

The `referrerPolicy` read-only property of the [`Request`](../request) interface returns the referrer policy, which governs what referrer information, sent in the [`Referer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referer) header, should be included with the request.

## Syntax

    var myReferrerPolicy = request.referrerPolicy;

### Value

A [`DOMString`](../domstring) representing the request's `referrerPolicy`. For more information and possible values, see the [`Referrer-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy) HTTP header page.

## Example

In the following snippet, we create a new request using the [`Request.Request()`](request) constructor (for an image file in the same directory as the script), then save the request referrer policy in a variable:

    var myRequest = new Request('flowers.jpg');
    var myReferrer = myRequest.referrerPolicy; // returns "" by default

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-request-referrerpolicy">Fetch<br />
<span class="small">The definition of 'referrerPolicy' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`referrerPolicy`

52

14

52

No

39

10.1

52

52

52

41

10.3

7.2

## See also

- [ServiceWorker API](../service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Request/referrerPolicy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Request/referrerPolicy</a>
