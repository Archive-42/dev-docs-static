# Request.clone()

The `clone()` method of the [`Request`](../request) interface creates a copy of the current `Request` object.

`clone()` throws a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) if the response [`Body`](../body) has already been used. In fact, the main reason `clone()` exists is to allow multiple uses of [`Body`](../body) objects (when they are one-use only.)

If intend to modify the request, you may prefer the [`Request`](../request) constructor.

## Syntax

    var newRequest = request.clone();

### Parameters

None.

### Return value

A [`Request`](../request) object, which is an exact copy of the `Request` that `clone()` was called on.

## Example

In the following snippet, we create a new request using the `Request.Request()` constructor (for an image file in the same directory as the script), then clone the request.

    var myRequest = new Request('flowers.jpg');
    var newRequest = myRequest.clone(); // a copy of the request is now stored in newRequest

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-request-clone">Fetch<br />
<span class="small">The definition of 'clone' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`clone`

42

41

14

39

34

No

29

28

10.1

No

No

No

29

28

10.3

No

## See also

- [ServiceWorker API](../service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Request/clone" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Request/clone</a>
