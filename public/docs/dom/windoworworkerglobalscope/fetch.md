WindowOrWorkerGlobalScope.fetch()
=================================

The `fetch()` method of the [`WindowOrWorkerGlobalScope`](../windoworworkerglobalscope) mixin starts the process of fetching a resource from the network, returning a promise which is fulfilled once the response is available. The promise resolves to the [`Response`](../response) object representing the response to your request. The promise *does not* reject on HTTP errors — it only rejects on network errors. You must use `then` handlers to check for HTTP errors.

`WindowOrWorkerGlobalScope` is implemented by both [`Window`](../window) and [`WorkerGlobalScope`](../workerglobalscope), which means that the `fetch()` method is available in pretty much any context in which you might want to fetch resources.

A [`fetch()`](fetch) promise only rejects when a network error is encountered (which is usually when there’s a permissions issue or similar). A [`fetch()`](fetch) promise *does not* reject on HTTP errors (`404`, etc.). Instead, a `then()` handler must check the [`Response.ok`](../response/ok) and/or [`Response.status`](../response/status) properties.

The `fetch()` method is controlled by the `connect-src` directive of [Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy) rather than the directive of the resources it's retrieving.

**Note**: The `fetch()` method's parameters are identical to those of the [`Request()`](../request/request) constructor.

Syntax
------

    const fetchResponsePromise = fetch(resource [, init])

### Parameters

`resource`  
This defines the resource that you wish to fetch. This can either be:

-   A string or any other object with a [stringifier](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Howto/Write_an_API_reference/Information_contained_in_a_WebIDL_file#stringifiers) — including a [`URL`](../url) object — that provides the URL of the resource you want to fetch.
-   A [`Request`](../request) object.

 `init` <span class="badge inline optional">Optional</span>   
An object containing any custom settings that you want to apply to the request. The possible options are:

`method`  
The request method, e.g., `GET`, `POST`. Note that the [`Origin`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Origin) header is not set on Fetch requests with a method of [`HEAD`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD) or [`GET`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET).  
(This behavior was corrected in Firefox 65 — see [bug 1508661](https://bugzilla.mozilla.org/show_bug.cgi?id=1508661)).

`headers`  
Any headers you want to add to your request, contained within a [`Headers`](../headers) object or an object literal with [`ByteString`](../bytestring) values. Note that [some names are forbidden](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name).

`body`  
Any body that you want to add to your request: this can be a [`Blob`](../blob), [`BufferSource`](../buffersource), [`FormData`](../formdata), [`URLSearchParams`](../urlsearchparams), [`USVString`](../usvstring), or [`ReadableStream`](../readablestream) object. Note that a request using the `GET` or `HEAD` method cannot have a body.

`mode`  
The mode you want to use for the request, e.g., `cors`, `no-cors`, or `same-origin`.

`credentials`  
Controls what browsers do with credentials ([cookies](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies), [HTTP authentication](https://developer.mozilla.org/en-US/docs/Web/HTTP/Authentication) entries, and TLS client certificates). Must be one of the following strings:

`omit`  
Tells browsers to exclude credentials from the request, and ignore any credentials sent back in the response (e.g., any [`Set-Cookie`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie) header).

`same-origin`  
Tells browsers to include credentials with requests to same-origin URLs, and use any credentials sent back in responses from same-origin URLs.

`include`  
Tells browsers to include credentials in both same- and cross-origin requests, and always use any credentials sent back in responses.

**Note**
Credentials may be included in simple and "final" cross-origin requests, but should not be included in [CORS preflight requests](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS#preflight_requests_and_credentials).

`cache`  
A string indicating how the request will interact with the browser’s [HTTP cache](https://developer.mozilla.org/en-US/docs/Web/HTTP/Caching). The possible values, `default`, `no-store`, `reload`, `no-cache`, `force-cache`, and `only-if-cached`, are documented in the article for the [`cache`](../request/cache) property of the [`Request`](../request) object.

`redirect`  
How to handle a `redirect` response:

-   `follow`: Automatically follow redirects. Unless otherwise stated the redirect mode is set to `follow`
-   `error`: Abort with an error if a redirect occurs.
-   `manual`: Caller intends to process the response in another context.  
    See [WHATWG fetch standard](https://fetch.spec.whatwg.org/#requests) for more information.

`referrer`  
A [`USVString`](../usvstring) specifying the referrer of the request. This can be a same-origin URL, `about:client`, or an empty string.

`referrerPolicy`  
Specifies the [referrer policy](https://w3c.github.io/webappsec-referrer-policy/#referrer-policies) to use for the request. May be one of `no-referrer`, `no-referrer-when-downgrade`, `same-origin`, `origin`, `strict-origin`, `origin-when-cross-origin`, `strict-origin-when-cross-origin`, or `unsafe-url`.

`integrity`  
Contains the [subresource integrity](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity) value of the request (e.g., `sha256-BpfBw7ivV8q2jLiT13fxDYAe2tJllusRSZ273h2nFSE=`).

`keepalive`  
The `keepalive` option can be used to allow the request to outlive the page. Fetch with the `keepalive` flag is a replacement for the [`Navigator.sendBeacon()`](../navigator/sendbeacon) API.

`signal`  
An [`AbortSignal`](../abortsignal) object instance; allows you to communicate with a fetch request and abort it if desired via an [`AbortController`](../abortcontroller).

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a [`Response`](../response) object.

### Exceptions

`AbortError`  
The request was aborted due to a call to the [`AbortController`](../abortcontroller) method [`abort()`](../abortcontroller/abort) method.

`TypeError`  
The specified URL string includes user credentials. This information should instead be provided using an [`Authorization`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization) header.

Examples
--------

In our [Fetch Request example](https://github.com/mdn/fetch-examples/tree/master/fetch-request) (see [Fetch Request live](https://mdn.github.io/fetch-examples/fetch-request/)) we create a new [`Request`](../request) object using the relevant constructor, then fetch it using a `fetch()` call. Since we are fetching an image, we run [`Body.blob()`](../body/blob) on the response to give it the proper MIME type so it will be handled properly, then create an Object URL of it and display it in an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element.

    const myImage = document.querySelector('img');

    let myRequest = new Request('flowers.jpg');

    fetch(myRequest)
    .then(function(response) {
      if (!response.ok) {
        throw new Error(`HTTP error! status: ${response.status}`);
      }
      return response.blob();
    })
    .then(function(response) {
      let objectURL = URL.createObjectURL(response);
      myImage.src = objectURL;
    });

In the [Fetch with init then Request example](https://github.com/mdn/fetch-examples/blob/master/fetch-with-init-then-request/index.html) (see [Fetch Request init live](https://mdn.github.io/fetch-examples/fetch-with-init-then-request/)), we do the same thing except that we pass in an `init` object when we invoke `fetch()`:

    const myImage = document.querySelector('img');

    let myHeaders = new Headers();
    myHeaders.append('Accept', 'image/jpeg');

    const myInit = {
      method: 'GET',
      headers: myHeaders,
      mode: 'cors',
      cache: 'default'
    };

    let myRequest = new Request('flowers.jpg');

    fetch(myRequest, myInit).then(function(response) {
      // ...
    });

You could also pass the `init` object in with the `Request` constructor to get the same effect:

    let myRequest = new Request('flowers.jpg', myInit);

You can also use an object literal as `headers` in `init`.

    const myInit = {
      method: 'GET',
      headers: {
        'Accept': 'image/jpeg'
      },
      mode: 'cors',
      cache: 'default'
    };

    let myRequest = new Request('flowers.jpg', myInit);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#fetch-method">Fetch<br />
<span class="small">The definition of 'fetch()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Defined in a <code>WindowOrWorkerGlobalScope</code> partial in the newest spec.</td></tr><tr class="even"><td><a href="https://fetch.spec.whatwg.org/#dom-global-fetch">Fetch<br />
<span class="small">The definition of 'fetch()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr><tr class="odd"><td><a href="https://w3c.github.io/webappsec-credential-management/">Credential Management Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds <a href="../federatedcredential"><code>FederatedCredential</code></a> or <a href="../passwordcredential"><code>PasswordCredential</code></a> instance as a possible value for <code>init.credentials</code>.</td></tr></tbody></table>

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

`fetch`

42

14

39

No

29

10.1

42

42

39

29

10.3

4.0

`blob_data_support`

48

79

?

No

?

?

43

48

?

?

?

5.0

`referrerpolicy`

52

79

52

No

39

11.1

52

52

52

41

No

6.0

`signal`

66

16

57

No

53

11.1

66

66

57

47

11.3

9.0

`streaming_response_body`

43

14

Yes

No

29

10.1

43

43

No

No

10.3

4.0

See also
--------

-   [Fetch API](../fetch_api)
-   [ServiceWorker API](../service_worker_api)
-   [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch</a>
