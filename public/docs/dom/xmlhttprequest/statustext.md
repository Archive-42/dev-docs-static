XMLHttpRequest.statusText
=========================

The read-only `XMLHttpRequest.statusText` property returns a [`DOMString`](../domstring) containing the response's status message as returned by the HTTP server. Unlike [`XMLHTTPRequest.status`](status) which indicates a numerical status code, this property contains the *text* of the response status, such as "OK" or "Not Found". If the request's `readyState` is in `UNSENT` or `OPENED` state, the value of `statusText` will be an empty string.

If the server response doesn't explicitly specify a status text, `statusText` will assume the default value "OK".

Responses over an HTTP/2 connection will always have a empty string as status message as HTTP/2 does not support them.

Example
-------

    var xhr = new XMLHttpRequest();
    console.log('0 UNSENT', xhr.statusText);

    xhr.open('GET', '/server', true);
    console.log('1 OPENED', xhr.statusText);

    xhr.onprogress = function () {
      console.log('3 LOADING', xhr.statusText);
    };

    xhr.onload = function () {
      console.log('4 DONE', xhr.statusText);
    };

    xhr.send(null);

    /**
     * Outputs the following:
     *
     * 0 UNSENT
     * 1 OPENED
     * 3 LOADING OK
     * 4 DONE OK
     */

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#the-statustext-attribute">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

1

12

1

7

Internet Explorer version 5 and 6 supported ajax calls using `ActiveXObject()`

Yes

1.2

1

18

4

Yes

Yes

1.0

See also
--------

-   List of [HTTP response codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)
-   [WHATWG Fetch Living Standard](https://fetch.spec.whatwg.org/#concept-response-status-message)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/statusText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/statusText</a>
