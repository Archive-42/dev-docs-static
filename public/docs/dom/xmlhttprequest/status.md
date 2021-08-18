XMLHttpRequest.status
=====================

The read-only `XMLHttpRequest.status` property returns the numerical HTTP [status code](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) of the `XMLHttpRequest`'s response.

Before the request completes, the value of `status` is 0. Browsers also report a status of 0 in case of `XMLHttpRequest` errors.

Example
-------

    var xhr = new XMLHttpRequest();
    console.log('UNSENT: ', xhr.status);

    xhr.open('GET', '/server');
    console.log('OPENED: ', xhr.status);

    xhr.onprogress = function () {
      console.log('LOADING: ', xhr.status);
    };

    xhr.onload = function () {
      console.log('DONE: ', xhr.status);
    };

    xhr.send();

    /**
     * Outputs the following:
     *
     * UNSENT: 0
     * OPENED: 0
     * LOADING: 200
     * DONE: 200
     */

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#the-status-attribute">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

1

12

1

7

Internet Explorer version 5 and 6 supported ajax calls using `ActiveXObject()`

8

1.2

1

18

4

10.1

1

1.0

See also
--------

-   List of [HTTP response codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)
-   [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/status" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/status</a>
