# Response

The `Response` interface of the [Fetch API](fetch_api) represents the response to a request.

You can create a new `Response` object using the [`Response.Response()`](response/response) constructor, but you are more likely to encounter a `Response` object being returned as the result of another API operation—for example, a service worker [`Fetchevent.respondWith`](fetchevent/respondwith), or a simple [`WindowOrWorkerGlobalScope.fetch()`](windoworworkerglobalscope/fetch).

## Constructor

[`Response()`](response/response)  
Creates a new `Response` object.

## Properties

[`Response.headers`](response/headers) <span class="badge inline readonly">Read only </span>  
The [`Headers`](headers) object associated with the response.

[`Response.ok`](response/ok) <span class="badge inline readonly">Read only </span>  
A boolean indicating whether the response was successful (status in the range `200`–`299`) or not.

[`Response.redirected`](response/redirected) <span class="badge inline readonly">Read only </span>  
Indicates whether or not the response is the result of a redirect (that is, its URL list has more than one entry).

[`Response.status`](response/status) <span class="badge inline readonly">Read only </span>  
The status code of the response. (This will be `200` for a success).

[`Response.statusText`](response/statustext) <span class="badge inline readonly">Read only </span>  
The status message corresponding to the status code. (e.g., `OK` for `200`).

<span class="page-not-created">`Response.trailers`</span>  
A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) resolving to a [`Headers`](headers) object, associated with the response with [`Response.headers`](response/headers) for values of the HTTP [`Trailer`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Trailer) header.

[`Response.type`](response/type) <span class="badge inline readonly">Read only </span>  
The type of the response (e.g., `basic`, `cors`).

[`Response.url`](response/url) <span class="badge inline readonly">Read only </span>  
The URL of the response.

### Body Interface Properties

`Response` implements [`Body`](body), so it also has the following properties available to it:

[`Body.body`](body/body) <span class="badge inline readonly">Read only </span>  
A simple getter exposing a [`ReadableStream`](readablestream) of the body contents.

[`Body.bodyUsed`](body/bodyused) <span class="badge inline readonly">Read only </span>  
Stores a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that declares whether the body has been used in a response yet.

## Methods

[`Response.clone()`](response/clone)  
Creates a clone of a `Response` object.

[`Response.error()`](response/error)  
Returns a new `Response` object associated with a network error.

[`Response.redirect()`](response/redirect)  
Creates a new response with a different URL.

### Body Interface Methods

`Response` implements [`Body`](body), so it also has the following methods available to it:

[`Body.arrayBuffer()`](body/arraybuffer)  
Takes a [`Response`](response) stream and reads it to completion. It returns a promise that resolves with an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer).

[`Body.blob()`](body/blob)  
Takes a [`Response`](response) stream and reads it to completion. It returns a promise that resolves with a [`Blob`](blob).

[`Body.formData()`](body/formdata)  
Takes a [`Response`](response) stream and reads it to completion. It returns a promise that resolves with a [`FormData`](formdata) object.

[`Body.json()`](body/json)  
Takes a [`Response`](response) stream and reads it to completion. It returns a promise that resolves with the result of parsing the body text as [`JSON`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON), which is a JavaScript value of datatype object, string, etc.

[`Body.text()`](body/text)  
Takes a [`Response`](response) stream and reads it to completion. It returns a promise that resolves with a [`USVString`](usvstring) (text).

## Examples

### Fetching an image

In our [basic fetch example](https://github.com/mdn/fetch-examples/tree/master/basic-fetch) ([run example live](https://mdn.github.io/fetch-examples/basic-fetch/)) we use a simple `fetch()` call to grab an image and display it in an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element. The `fetch()` call returns a promise, which resolves to the `Response` object associated with the resource fetch operation.

You'll notice that since we are requesting an image, we need to run [`Body.blob`](body/blob) ([`Response`](response) implements Body) to give the response its correct MIME type.

    const image = document.querySelector('.my-image');
    fetch('flowers.jpg')
    .then(response => response.blob())
    .then(blob => {
      const objectURL = URL.createObjectURL(blob);
      image.src = objectURL;
    });

You can also use the [`Response.Response()`](response/response) constructor to create your own custom `Response` object:

    const response = new Response();

### An Ajax Call

Here we call a PHP program file that generates a JSON string, displaying the result as a JSON value, including simple error handling.

    // Function to do an Ajax call
    const doAjax = async () => {
      const response = await fetch('Ajax.php'); // Generate the Response object
      if (response.ok) {
        const jsonValue = await response.json(); // Get JSON value from the response body
        return Promise.resolve(jsonValue);
      } else {
        return Promise.reject('*** PHP file not found');
      }
    }

    // Call the function and output value or error message to console
    doAjax().then(console.log).catch(console.log);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#response-class">Fetch<br />
<span class="small">The definition of 'Response' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

39

34

29

28

10.3

4.0

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

`error`

Yes

16

Yes

No

Yes

Yes

No

No

No

No

No

No

`headers`

42

41

14

39

34

No

29

28

No

No

42

No

29

28

No

4.0

`ok`

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

`redirect`

Yes

16

Yes

No

Yes

Yes

No

No

No

No

No

No

`redirected`

60

16

49

No

47

No

60

60

49

44

No

8.0

`status`

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

`statusText`

42

41

14

39

34

No

29

28

No

No

No

No

29

28

No

No

`type`

42

41

14

39

34

No

29

28

No

No

No

No

29

28

No

No

`url`

42

41

14

39

34

No

29

28

No

No

No

No

29

28

No

No

## See also

- [ServiceWorker API](service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Response" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Response</a>
