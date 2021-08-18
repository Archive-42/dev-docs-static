Response.statusText
===================

The `statusText` read-only property of the [`Response`](../response) interface contains the status message corresponding to the status code (e.g., `OK` for `200`).

Syntax
------

    var myStatusText = response.statusText;

### Value

A [`ByteString`](../bytestring).

The default value is "". Note that HTTP/2 [does not support](https://fetch.spec.whatwg.org/#concept-response-status-message) status messages.

Example
-------

In our [Fetch Response example](https://github.com/mdn/fetch-examples/tree/gh-pages/fetch-response) (see [Fetch Response live](https://mdn.github.io/fetch-examples/fetch-response/)) we create a new [`Request`](../request) object using the [`Request()`](../request/request) constructor, passing it a JPG path. We then fetch this request using [`fetch()`](../windoworworkerglobalscope/fetch), extract a blob from the response using [`Body.blob`](../body/blob), create an object URL out of it using [`URL.createObjectURL`](../url/createobjecturl), and display this in an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img).

Note that at the top of the `fetch()` block we log the response `statusText` value to the console.

    var myImage = document.querySelector('img');

    var myRequest = new Request('flowers.jpg');

    fetch(myRequest).then(function(response) {
      console.log(response.statusText); // returns "OK" if the response returned successfully
      response.blob().then(function(myBlob) {
        var objectURL = URL.createObjectURL(myBlob);
        myImage.src = objectURL;
      });
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#dom-response-statustext">Fetch<br />
<span class="small">The definition of 'statusText' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

See also
--------

-   [ServiceWorker API](../service_worker_api)
-   [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Response/statusText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Response/statusText</a>
