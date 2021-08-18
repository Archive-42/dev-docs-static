# Request()

The `Request()` constructor creates a new [`Request`](../request) object.

## Syntax

    var myRequest = new Request(input[, init]);

### Parameters

_input_  
Defines the resource that you wish to fetch. This can either be:

- A [`USVString`](../usvstring) containing the direct URL of the resource you want to fetch.
- A [`Request`](../request) object, effectively creating a copy. Note the following behavioral updates to retain security while making the constructor less likely to throw exceptions:
  - If this object exists on another origin to the constructor call, the [`Request.referrer`](referrer) is stripped out.
  - If this object has a [`Request.mode`](mode) of `navigate`, the `mode` value is converted to `same-origin`.

_init_ <span class="badge inline optional">Optional</span>  
An options object containing any custom settings that you want to apply to the request. The possible options are:

- `method`: The request method, e.g., `GET`, `POST`. The default is `GET`.
- `headers`: Any headers you want to add to your request, contained within a [`Headers`](../headers) object or an object literal with [`ByteString`](../bytestring) values.
- `body`: Any body that you want to add to your request: this can be a [`Blob`](../blob), [`BufferSource`](../buffersource), [`FormData`](../formdata), [`URLSearchParams`](../urlsearchparams), [`USVString`](../usvstring), or [`ReadableStream`](../readablestream) object. Note that a request using the `GET` or `HEAD` method cannot have a body.
- `mode`: The mode you want to use for the request, e.g., `cors`, `no-cors`, `same-origin`, or `navigate`. The default is `cors`.
- `credentials`: The request credentials you want to use for the request: `omit`, `same-origin`, or `include`. The default is `same-origin`.
- `cache`: The [cache mode](cache) you want to use for the request.
- `redirect`: The redirect mode to use: `follow`, `error`, or `manual`. The default is `follow`.
- `referrer`: A [`USVString`](../usvstring) specifying `no-referrer`, `client`, or a URL. The default is `about:client`.
- `integrity`: Contains the [subresource integrity](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity) value of the request (e.g., `sha256-BpfBw7ivV8q2jLiT13fxDYAe2tJllusRSZ273h2nFSE=`).

## Errors

<table><thead><tr class="header"><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>TypeError</code></td><td>Since <a href="https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/43">Firefox 43</a>, <code>Request()</code> will throw a TypeError if the URL has credentials, such as http://user:password@example.com.</td></tr></tbody></table>

## Example

In our [Fetch Request example](https://github.com/mdn/fetch-examples/tree/master/fetch-request) (see [Fetch Request live](https://mdn.github.io/fetch-examples/fetch-request/)) we create a new `Request` object using the constructor, then fetch it using a [`WindowOrWorkerGlobalScope.fetch`](../windoworworkerglobalscope/fetch) call. Since we are fetching an image, we run [`Body.blob`](../body/blob) on the response to give it the proper MIME type so it will be handled properly, then create an Object URL of it and display it in an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element.

    var myImage = document.querySelector('img');

    var myRequest = new Request('flowers.jpg');

    fetch(myRequest).then(function(response) {
      return response.blob();
    }).then(function(response) {
      var objectURL = URL.createObjectURL(response);
      myImage.src = objectURL;
    });

In our [Fetch Request with init example](https://github.com/mdn/fetch-examples/tree/master/fetch-request-with-init) (see [Fetch Request init live](https://mdn.github.io/fetch-examples/fetch-request-with-init/)) we do the same thing except that we pass in an init object when we invoke `fetch()`:

    var myImage = document.querySelector('img');

    var myHeaders = new Headers();
    myHeaders.append('Content-Type', 'image/jpeg');

    var myInit = { method: 'GET',
                   headers: myHeaders,
                   mode: 'cors',
                   cache: 'default' };

    var myRequest = new Request('flowers.jpg',myInit);

    fetch(myRequest).then(function(response) {
      ...
    });

Note that you could also pass the init object into the `fetch` call to get the same effect, e.g.:

    fetch(myRequest,myInit).then(function(response) {
      ...
    });

You can also use an object literal as `headers` in `init`.

    var myInit = { method: 'GET',
                   headers: {
                       'Content-Type': 'image/jpeg'
                   },
                   mode: 'cors',
                   cache: 'default' };

    var myRequest = new Request('flowers.jpg', myInit);

You may also pass a [`Request`](../request) object to the `Request()` constructor to create a copy of the Request (This is similar to calling the [`clone()`](clone) method.)

    var copy = new Request(myRequest);

**Note**: This last usage is probably only useful in [ServiceWorkers](../service_worker_api).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-request">Fetch<br />
<span class="small">The definition of 'Request()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`Request`

41

From Chrome 47, default values for the `init` argument's properties changed. `mode` defaults to `same-origin` (from `no-cors`). `credentials` defaults to `include` (from `same-origin`). `redirect` defaults to `follow` (from `manual`).

15

39

34

No

29

28

10.1

42

From WebView 47, default values for the `init` argument's properties changed. `mode` defaults to `same-origin` (from `no-cors`). `credentials` defaults to `include` (from `same-origin`). `redirect` defaults to `follow` (from `manual`).

41

From Chrome 47, default values for the `init` argument's properties changed. `mode` defaults to `same-origin` (from `no-cors`). `credentials` defaults to `include` (from `same-origin`). `redirect` defaults to `follow` (from `manual`).

39

34

29

28

10.3

4.0

5.0

Some default values for the init parameter changed in Samsung Internet 5.0. See the Properties section for details.

`cross_origin_stripped`

Yes

15

54

No

Yes

10.1

Yes

Yes

Yes

No

10.3

Yes

`navigate_mode`

49

15

46

No

Yes

10.1

No

49

Yes

No

10.3

5.0

`readablestream_request_body`

No

No

No

No

?

No

No

No

No

No

No

No

`referrer_init`

?

15

47

No

Yes

10.1

Yes

Yes

Yes

No

10.3

Yes

`reponse_body_readablestream`

43

≤79

65

57

No

?

No

43

43

65

57

No

10.3

4.0

## See also

- [ServiceWorker API](../service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Request/Request" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Request/Request</a>
