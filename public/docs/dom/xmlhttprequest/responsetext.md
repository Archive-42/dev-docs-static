XMLHttpRequest.responseText
===========================

**Draft**

This page is not complete.

The read-only [`XMLHttpRequest`](../xmlhttprequest) property `responseText` returns the text received from a server following a request being sent.

Syntax
------

    var resultText = XMLHttpRequest.responseText;

### Value

A [`DOMString`](../domstring) which contains either the textual data received using the `XMLHttpRequest` or `null` if the request failed or `""` if the request has not yet been sent by calling [`send()`](send).

While handling an asynchronous request, the value of `responseText` always has the current content received from the server, even if it's incomplete because the data has not been completely received yet.

You know the entire content has been received when the value of [`readyState`](readystate) becomes <span class="page-not-created">`XMLHttpRequest.DONE`</span> (`4`), and [`status`](status) becomes 200 (`"OK"`).

### Exceptions

`InvalidStateError`  
The [`XMLHttpRequest.responseType`](responsetype) is not set to either the empty string or `"text"`. Since the `responseText` property is only valid for text content, any other value is an error condition.

Example
-------

    var xhr = new XMLHttpRequest();
    xhr.open('GET', '/server', true);

    // If specified, responseType must be empty string or "text"
    xhr.responseType = 'text';

    xhr.onload = function () {
        if (xhr.readyState === xhr.DONE) {
            if (xhr.status === 200) {
                console.log(xhr.response);
                console.log(xhr.responseText);
            }
        }
    };

    xhr.send(null);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#the-responsetext-attribute">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`responseText`

1

12

1

5

Before Internet Explorer 10, the value of `XMLHttpRequest.responseText` could be read only once the request was complete.

8

1.2

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseText</a>
