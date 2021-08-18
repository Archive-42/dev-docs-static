# Body.blob()

The `blob()` method of the [`Body`](../body) mixin takes a [`Response`](../response) stream and reads it to completion. It returns a promise that resolves with a [`Blob`](../blob).

## Syntax

    response.blob().then(function(myBlob) {
      // do something with myBlob
    });

### Parameters

None.

**Note:** If the [`Response`](../response) has a [`Response.type`](../response/type) of `"opaque"`, the resulting [`Blob`](../blob) will have a [`Blob.size`](../blob/size) of `0` and a [`Blob.type`](../blob/type) of empty string `""`, which renders it _useless_ for methods like [`URL.createObjectURL`](../url/createobjecturl).

### Return value

A promise that resolves with a [`Blob`](../blob).

## Example

In our [fetch request example](https://github.com/mdn/fetch-examples/tree/master/fetch-request) (run [fetch request live](https://mdn.github.io/fetch-examples/fetch-request/)), we create a new request using the [`Request()`](../request/request) constructor, then use it to fetch a JPG. When the fetch is successful, we read a [`Blob`](../blob) out of the response using `blob()`, put it into an object URL using [`URL.createObjectURL`](../url/createobjecturl), and then set that URL as the source of an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element to display the image.

    var myImage = document.querySelector('img');

    var myRequest = new Request('flowers.jpg');

    fetch(myRequest)
    .then(response => response.blob())
    .then(function(myBlob) {
      var objectURL = URL.createObjectURL(myBlob);
      myImage.src = objectURL;
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-body-blob">Fetch<br />
<span class="small">The definition of 'blob()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`blob`

42

≤18

39

No

29

10.1

No

42

No

29

10.3

4.0

## See also

- [ServiceWorker API](../service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Body/blob" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Body/blob</a>
