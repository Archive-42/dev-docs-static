# Response()

The `Response()` constructor creates a new [`Response`](../response) object.

## Syntax

    var myResponse = new Response(body, init);

### Parameters

_body_ <span class="badge inline optional">Optional</span>  
An object defining a body for the response. This can be `null` (which is the default value), or one of:

- [`Blob`](../blob)
- [`BufferSource`](../buffersource)
- [`FormData`](../formdata)
- [`ReadableStream`](../readablestream)
- [`URLSearchParams`](../urlsearchparams)
- [`USVString`](../usvstring)

_init_ <span class="badge inline optional">Optional</span>  
An options object containing any custom settings that you want to apply to the response, or an empty object (which is the default value). The possible options are:

- `status`: The status code for the response, e.g., `200`.
- `statusText`: The status message associated with the status code, e.g., `OK`.
- `headers`: Any headers you want to add to your response, contained within a [`Headers`](../headers) object or object literal of [`ByteString`](../bytestring) key/value pairs (see [HTTP headers](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers) for a reference).

## Examples

In our [Fetch Response example](https://github.com/mdn/fetch-examples/tree/master/fetch-response) (see [Fetch Response live](https://mdn.github.io/fetch-examples/fetch-response/)) we create a new `Response` object using the constructor, passing it a new [`Blob`](../blob) as a body, and an init object containing a custom `status` and `statusText`:

    var myBlob = new Blob();
    var init = { "status" : 200 , "statusText" : "SuperSmashingGreat!" };
    var myResponse = new Response(myBlob,init);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-response">Fetch<br />
<span class="small">The definition of 'Response()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`Response`

42

41

14

39

34

No

29

28

10.1

42

42

41

Yes

29

28

10.3

4.0

`accept_readablestream`

52

≤79

No

No

39

No

52

52

No

41

10.3

6.0

`body_param_null`

Yes

≤79

59

No

Yes

No

Yes

Yes

Yes

Yes

No

Yes

## See also

- [ServiceWorker API](../service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Response/Response" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Response/Response</a>
