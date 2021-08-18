# Body.bodyUsed

The `bodyUsed` read-only property of the [`Body`](../body) mixin contains a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the body has been read yet.

## Syntax

    var myBodyUsed = response.bodyUsed;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

## Example

In our [fetch request example](https://github.com/mdn/fetch-examples/tree/master/fetch-request) (run [fetch request live](https://mdn.github.io/fetch-examples/fetch-request/)), we create a new request using the [`Request()`](../request/request) constructor, then use it to fetch a JPG. When the fetch is successful, we read a [`Blob`](../blob) out of the response using `blob()`, put it into an object URL using [`URL.createObjectURL`](../url/createobjecturl), and then set that URL as the source of an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element to display the image.

Notice that we log `response.bodyUsed` to the console once before the `response.blob()` call and once after. This returns `false` before and `true` afterwards, as at that point the body has been read.

### HTML Content

    <img class="my-image" src="https://wikipedia.org/static/images/project-logos/frwiki-1.5x.png">

### JS Content

    var myImage = document.querySelector('.my-image');
    fetch('https://upload.wikimedia.org/wikipedia/commons/7/77/Delete_key1.jpg').then(function(response) {
        console.log(response.bodyUsed);
        var res = response.blob();
        console.log(response.bodyUsed);
        return res;
    }).then(function(response) {
        var objectURL = URL.createObjectURL(response);
        myImage.src = objectURL;
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-body-bodyused">Fetch<br />
<span class="small">The definition of 'bodyUsed' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`bodyUsed`

42

≤18

39

No

29

10.1

No

No

No

29

10.3

No

## See also

- [ServiceWorker API](../service_worker_api)
- [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
- [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Body/bodyUsed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Body/bodyUsed</a>
