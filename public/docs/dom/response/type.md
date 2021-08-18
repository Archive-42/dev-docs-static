# Response.type

The `type` read-only property of the [`Response`](../response) interface contains the type of the response. It can be one of the following:

- `basic`: Normal, same origin response, with all headers exposed except “Set-Cookie” and “Set-Cookie2″.
- `cors`: Response was received from a valid cross-origin request. [Certain headers and the body](https://fetch.spec.whatwg.org/#concept-filtered-response-cors) may be accessed.
- `error`: Network error. No useful information describing the error is available. The Response’s status is 0, headers are empty and immutable. This is the type for a Response obtained from `Response.error()`.
- `opaque`: Response for “no-cors” request to cross-origin resource. [Severely restricted](https://fetch.spec.whatwg.org/#concept-filtered-response-opaque).
- `opaqueredirect`: The fetch request was made with `redirect: "manual"`. The Response's status is 0, headers are empty, body is null and trailer is empty.

**Note**: An "error" Response never really gets exposed to script: such a response to a [`fetch()`](../windoworworkerglobalscope/fetch) would reject the promise.

## Syntax

    var myType = response.type;

### Value

A `ResponseType` string indicating the type of the response.

## Example

In our [Fetch Response example](https://github.com/mdn/fetch-examples/tree/gh-pages/fetch-response) (see [Fetch Response live](https://mdn.github.io/fetch-examples/fetch-response/)) we create a new [`Request`](../request) object using the [`Request()`](../request/request) constructor, passing it a JPG path. We then fetch this request using [`fetch()`](../windoworworkerglobalscope/fetch), extract a blob from the response using [`Body.blob`](../body/blob), create an object URL out of it using [`URL.createObjectURL`](../url/createobjecturl), and display this in an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img).

Note that at the top of the `fetch()` block we log the response `type` to the console.

    var myImage = document.querySelector('img');

    var myRequest = new Request('flowers.jpg');

    fetch(myRequest).then(function(response) {
      console.log(response.type); // returns basic by default
      response.blob().then(function(myBlob) {
        var objectURL = URL.createObjectURL(myBlob);
        myImage.src = objectURL;
      });
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-response-type">Fetch<br />
<span class="small">The definition of 'type' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

## See also

- [ServiceWorker API](../service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Response/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Response/type</a>
