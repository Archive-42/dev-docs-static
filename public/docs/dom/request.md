# Request

The `Request` interface of the [Fetch API](fetch_api) represents a resource request.

You can create a new `Request` object using the [`Request()`](request/request) constructor, but you are more likely to encounter a `Request` object being returned as the result of another API operation, such as a service worker [`FetchEvent.request`](fetchevent/request).

## Constructor

[`Request()`](request/request)  
Creates a new `Request` object.

## Properties

[`Request.cache`](request/cache) <span class="badge inline readonly">Read only </span>  
Contains the cache mode of the request (e.g., `default`, `reload`, `no-cache`).

[`Request.context`](request/context) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Contains the context of the request (e.g., `audio`, `image`, `iframe`, etc.)

[`Request.credentials`](request/credentials) <span class="badge inline readonly">Read only </span>  
Contains the credentials of the request (e.g., `omit`, `same-origin`, `include`). The default is `same-origin`.

[`Request.destination`](request/destination) <span class="badge inline readonly">Read only </span>  
Returns a string from the [`RequestDestination`](requestdestination) enum describing the request's destination. This is a string indicating the type of content being requested.

[`Request.headers`](request/headers) <span class="badge inline readonly">Read only </span>  
Contains the associated [`Headers`](headers) object of the request.

[`Request.integrity`](request/integrity) <span class="badge inline readonly">Read only </span>  
Contains the [subresource integrity](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity) value of the request (e.g., `sha256-BpfBw7ivV8q2jLiT13fxDYAe2tJllusRSZ273h2nFSE=`).

[`Request.method`](request/method) <span class="badge inline readonly">Read only </span>  
Contains the request's method (`GET`, `POST`, etc.)

[`Request.mode`](request/mode) <span class="badge inline readonly">Read only </span>  
Contains the mode of the request (e.g., `cors`, `no-cors`, `same-origin`, `navigate`.)

[`Request.redirect`](request/redirect) <span class="badge inline readonly">Read only </span>  
Contains the mode for how redirects are handled. It may be one of `follow`, `error`, or `manual`.

[`Request.referrer`](request/referrer) <span class="badge inline readonly">Read only </span>  
Contains the referrer of the request (e.g., `client`).

[`Request.referrerPolicy`](request/referrerpolicy) <span class="badge inline readonly">Read only </span>  
Contains the referrer policy of the request (e.g., `no-referrer`).

[`Request.url`](request/url) <span class="badge inline readonly">Read only </span>  
Contains the URL of the request.

`Request` implements [`Body`](body), so it also inherits the following properties:

[`body`](body/body) <span class="badge inline readonly">Read only </span>  
A simple getter used to expose a [`ReadableStream`](readablestream) of the body contents.

[`bodyUsed`](body/bodyused) <span class="badge inline readonly">Read only </span>  
Stores a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that declares whether the body has been used in a response yet.

## Methods

[`Request.clone()`](request/clone)  
Creates a copy of the current `Request` object.

`Request` implements [`Body`](body), so it also has the following methods available to it:

[`Body.arrayBuffer()`](body/arraybuffer)  
Returns a promise that resolves with an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) representation of the request body.

[`Body.blob()`](body/blob)  
Returns a promise that resolves with a [`Blob`](blob) representation of the request body.

[`Body.formData()`](body/formdata)  
Returns a promise that resolves with a [`FormData`](formdata) representation of the request body.

[`Body.json()`](body/json)  
Returns a promise that resolves with a <span class="page-not-created">`JSON`</span> representation of the request body.

[`Body.text()`](body/text)  
Returns a promise that resolves with an [`USVString`](usvstring) (text) representation of the request body.

**Note**: The [`Body`](body) functions can be run only once; subsequent calls will resolve with empty strings/ArrayBuffers.

## Examples

In the following snippet, we create a new request using the `Request()` constructor (for an image file in the same directory as the script), then return some property values of the request:

    const request = new Request('https://www.mozilla.org/favicon.ico');

    const url = request.url;
    const method = request.method;
    const credentials = request.credentials;

You could then fetch this request by passing the `Request` object in as a parameter to a [`WindowOrWorkerGlobalScope.fetch()`](windoworworkerglobalscope/fetch) call, for example:

    fetch(request)
      .then(response => response.blob())
      .then(blob => {
        image.src = URL.createObjectURL(blob);
      });

In the following snippet, we create a new request using the `Request()` constructor with some initial data and body content for an api request which need a body payload:

    const request = new Request('https://example.com', {method: 'POST', body: '{"foo": "bar"}'});

    const url = request.url;
    const method = request.method;
    const credentials = request.credentials;
    const bodyUsed = request.bodyUsed;

**Note:** The body type can only be a [`Blob`](blob), [`BufferSource`](buffersource), [`FormData`](formdata), [`URLSearchParams`](urlsearchparams), [`USVString`](usvstring) or [`ReadableStream`](readablestream) type, so for adding a JSON object to the payload you need to stringify that object.

You could then fetch this api request by passing the `Request` object in as a parameter to a [`WindowOrWorkerGlobalScope.fetch()`](windoworworkerglobalscope/fetch) call, for example and get the response:

    fetch(request)
      .then(response => {
        if (response.status === 200) {
          return response.json();
        } else {
          throw new Error('Something went wrong on api server!');
        }
      })
      .then(response => {
        console.debug(response);
        // ...
      }).catch(error => {
        console.error(error);
      });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#request-class">Fetch<br />
<span class="small">The definition of 'Request' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

42

41

≤18

39

34

No

28

10.1

42

42

41

39

34

28

10.3

4.0

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

`cache`

64

14

48

No

51

10.1

64

64

No

47

10.3

9.0

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

`context`

42-46

?

39-42

see [bug 1188062](https://bugzil.la/1188062) for more information.

No

28-29

No

42-46

42-46

No

No

No

4.0-5.0

`credentials`

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

39

29

28

10.3

4.0

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

`headers`

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

39

29

28

10.3

4.0

`integrity`

46

14

51

No

Yes

10.1

No

46

51

Yes

10.3

5.0

`isHistoryNavigation`

69

79

No

No

56

No

69

69

No

48

No

10.0

`keepalive`

66

15

No

No

43

No

66

66

No

43

No

9.0

`method`

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

39

29

28

10.3

4.0

`mode`

42

14

39

No

29

10.1

49

49

39

No

10.3

5.0

`redirect`

46

14

43

No

Yes

10.1

No

46

43

Yes

10.3

5.0

`referrer`

42

41

14

47

No

29

28

10.1

42

42

No

29

28

10.3

4.0

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

`signal`

66

16

57

No

Yes

12.1

66

66

57

Yes

12.2

9.0

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

- [ServiceWorker API](service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Request" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Request</a>
