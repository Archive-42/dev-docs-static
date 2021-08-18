Response.clone()
================

The `clone()` method of the [`Response`](../response) interface creates a clone of a response object, identical in every way, but stored in a different variable.

`clone()` throws a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError) if the response [`Body`](../body) has already been used. In fact, the main reason `clone()` exists is to allow multiple uses of [`Body`](../body) objects (when they are one-use only.)

Syntax
------

    var response2 = response1.clone();

### Parameters

None.

### Value

A [`Response`](../response) object.

Example
-------

In our [Fetch Response clone example](https://github.com/mdn/fetch-examples/tree/gh-pages/fetch-response-clone) (see [Fetch Response clone live](https://mdn.github.io/fetch-examples/fetch-response-clone/)) we create a new [`Request`](../request) object using the [`Request()`](../request/request) constructor, passing it a JPG path. We then fetch this request using [`fetch()`](../windoworworkerglobalscope/fetch). When the fetch resolves successfully, we clone it, extract a blob from both responses using two [`Body.blob`](../body/blob) calls, create object URLs out of the blobs using [`URL.createObjectURL`](../url/createobjecturl), and display them in two separate [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) elements.

    var image1 = document.querySelector('.img1');
    var image2 = document.querySelector('.img2');

    var myRequest = new Request('flowers.jpg');

    fetch(myRequest).then(function(response) {
      var response2 = response.clone();

      response.blob().then(function(myBlob) {
        var objectURL = URL.createObjectURL(myBlob);
        image1.src = objectURL;
      });

      response2.blob().then(function(myBlob) {
        var objectURL = URL.createObjectURL(myBlob);
        image2.src = objectURL;
      });
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-response-clone">Fetch<br />
<span class="small">The definition of 'clone()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

-   [ServiceWorker API](../service_worker_api)
-   [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Response/clone" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Response/clone</a>
