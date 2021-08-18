# Response.headers

The `headers` read-only property of the [`Response`](../response) interface contains the [`Headers`](../headers) object associated with the response.

## Syntax

    var myHeaders = response.headers;

### Value

A [`Headers`](../headers) object.

## Example

In our [Fetch Response example](https://github.com/mdn/fetch-examples/tree/master/fetch-response) (see [Fetch Response live](https://mdn.github.io/fetch-examples/fetch-response/)) we create a new [`Request`](../request) object using the [`Request()`](../request/request) constructor, passing it a JPG path. We then fetch this request using [`fetch()`](../windoworworkerglobalscope/fetch), extract a blob from the response using [`Body.blob`](../body/blob), create an object URL out of it using [`URL.createObjectURL`](../url/createobjecturl), and display this in an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img).

Note that at the top of the `fetch()` block we log the response `headers` value to the console.

    var myImage = document.querySelector('img');

    var myRequest = new Request('flowers.jpg');

    fetch(myRequest).then(function(response) {
      console.log(response.headers); // returns a Headers{} object
      response.blob().then(function(myBlob) {
        var objectURL = URL.createObjectURL(myBlob);
        myImage.src = objectURL;
      });
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-response-headers">Fetch<br />
<span class="small">The definition of 'headers' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

## See also

- [ServiceWorker API](../service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Response/headers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Response/headers</a>
