XMLHttpRequest.abort()
======================

The `XMLHttpRequest.abort()` method aborts the request if it has already been sent. When a request is aborted, its [`readyState`](readystate) is changed to <span class="page-not-created">`XMLHttpRequest.UNSENT`</span> (0) and the request's [`status`](status) code is set to 0.

Syntax
------

    XMLHttpRequest.abort()

### Parameters

None.

### Return value

`undefined`

Example
-------

This example begins loading content from the MDN home page, then due to some condition, aborts the transfer by calling `abort()`.

    var xhr = new XMLHttpRequest(),
        method = "GET",
        url = "https://developer.mozilla.org/";
    xhr.open(method, url, true);

    xhr.send();

    if (OH_NOES_WE_NEED_TO_CANCEL_RIGHT_NOW_OR_ELSE) {
      xhr.abort();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#the-abort()-method">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`abort`

18

12

Yes

5

Yes

1.2

≤37

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [Using XMLHttpRequest](using_xmlhttprequest)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/abort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/abort</a>
