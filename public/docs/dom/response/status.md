Response.status
===============

The `status` read-only property of the [`Response`](../response) interface contains the status code of the response (e.g., `200` for a success).

Syntax
------

    var myStatus = response.status;

### Value

A number (to be precise, an unsigned short).

Example
-------

In our [Fetch Response example](https://github.com/mdn/fetch-examples/tree/master/fetch-response) (see [Fetch Response live](https://mdn.github.io/fetch-examples/fetch-response/)) we create a new [`Request`](../request) object using the [`Request()`](../request/request) constructor, passing it a JPG path. We then fetch this request using [`fetch()`](../windoworworkerglobalscope/fetch), extract a blob from the response using [`Body.blob`](../body/blob), create an object URL out of it using [`URL.createObjectURL`](../url/createobjecturl), and display this in an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img).

Note that at the top of the `fetch()` block we log the response `status` value to the console.

    var myImage = document.querySelector('img');

    var myRequest = new Request('flowers.jpg');

    fetch(myRequest).then(function(response) {
      console.log(response.status); // returns 200
      response.blob().then(function(myBlob) {
        var objectURL = URL.createObjectURL(myBlob);
        myImage.src = objectURL;
      });
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-response-status">Fetch<br />
<span class="small">The definition of 'status' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

-   [ServiceWorker API](../service_worker_api)
-   [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Response/status" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Response/status</a>
