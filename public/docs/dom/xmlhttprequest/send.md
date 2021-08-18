XMLHttpRequest.send()
=====================

The [`XMLHttpRequest`](../xmlhttprequest) method `send()` sends the request to the server. If the request is asynchronous (which is the default), this method returns as soon as the request is sent and the result is delivered using events. If the request is synchronous, this method doesn't return until the response has arrived.

`send()` accepts an optional parameter which lets you specify the request's body; this is primarily used for requests such as [`PUT`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT). If the request method is [`GET`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) or [`HEAD`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD), the `body` parameter is ignored and the request body is set to `null`.

If no [`Accept`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept) header has been set using the [`setRequestHeader()`](setrequestheader), an `Accept` header with the type `"*/*"` (any type) is sent.

Syntax
------

    XMLHttpRequest.send(body)

### Parameters

 `body` <span class="badge inline optional">Optional</span>   
A body of data to be sent in the XHR request. This can be:

-   A [`Document`](../document), in which case it is serialized before being sent.
-   An `XMLHttpRequestBodyInit`, which [per the Fetch spec](https://fetch.spec.whatwg.org/#typedefdef-xmlhttprequestbodyinit) can be a [`Blob`](../blob), [`BufferSource`](../buffersource), [`FormData`](../formdata), [`URLSearchParams`](../urlsearchparams), or [`USVString`](../usvstring) object.
-   `null`

If no value is specified for the body, a default value of `null` is used.

The best way to send binary content (e.g. in file uploads) is by using an [`ArrayBufferView`](../arraybufferview) or [`Blob`](../blob) in conjunction with the `send()` method.

### Return value

`undefined`.

### Exceptions

<table><thead><tr class="header"><th>Exception</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>InvalidStateError</code></td><td><code>send()</code> has already been invoked for the request, and/or the request is complete.</td></tr><tr class="even"><td><code>NetworkError</code></td><td>The resource type to be fetched is a Blob, and the method is not <code>GET</code>.</td></tr></tbody></table>

Example: GET
------------

    var xhr = new XMLHttpRequest();
    xhr.open('GET', '/server', true);

    xhr.onload = function () {
      // Request finished. Do processing here.
    };

    xhr.send(null);
    // xhr.send('string');
    // xhr.send(new Blob());
    // xhr.send(new Int8Array());
    // xhr.send(document);

Example: POST
-------------

    var xhr = new XMLHttpRequest();
    xhr.open("POST", '/server', true);

    //Send the proper header information along with the request
    xhr.setRequestHeader("Content-Type", "application/x-www-form-urlencoded");

    xhr.onreadystatechange = function() { // Call a function when the state changes.
        if (this.readyState === XMLHttpRequest.DONE && this.status === 200) {
            // Request finished. Do processing here.
        }
    }
    xhr.send("foo=bar&lorem=ipsum");
    // xhr.send(new Int8Array());
    // xhr.send(document);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#the-send()-method">XMLHttpRequest<br />
<span class="small">The definition of 'send()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`send`

1

12

1

5

8

1.2

1

18

4

10.1

1

1.0

`ArrayBuffer`

9

12

9

10

11.6

Yes

≤37

Yes

9

Yes

?

Yes

`ArrayBufferView`

22

≤79

20

?

Yes

?

≤37

Yes

20

Yes

?

Yes

`Blob`

22

12

2

10

12

?

≤37

Yes

4

Yes

?

Yes

`FormData`

6

12

2

10

12

?

≤37

Yes

4

Yes

?

Yes

`URLSearchParams`

59

≤79

44

?

12

?

59

59

44

Yes

?

7.0

See also
--------

-   [Using XMLHttpRequest](using_xmlhttprequest)
-   [HTML in XMLHttpRequest](html_in_xmlhttprequest)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/send" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/send</a>
