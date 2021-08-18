XMLHttpRequest.withCredentials
==============================

The `XMLHttpRequest.withCredentials` property is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether or not cross-site `Access-Control` requests should be made using credentials such as cookies, authorization headers or TLS client certificates. Setting `withCredentials` has no effect on same-site requests.

In addition, this flag is also used to indicate when cookies are to be ignored in the response. The default is `false`. `XMLHttpRequest` from a different domain cannot set cookie values for their own domain unless `withCredentials` is set to `true` before making the request. The third-party cookies obtained by setting `withCredentials` to true will still honor same-origin policy and hence can not be accessed by the requesting script through [document.cookie](../document/cookie) or from response headers.

**Note:** This never affects same-site requests.

**Note:** `XMLHttpRequest` responses from a different domain *cannot* set cookie values for their own domain unless `withCredentials` is set to `true` before making the request, regardless of `Access-Control-` header values.

Example
-------

    var xhr = new XMLHttpRequest();
    xhr.open('GET', 'http://example.com/', true);
    xhr.withCredentials = true;
    xhr.send(null);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#the-withcredentials-attribute">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`withCredentials`

3

12

3.5

Starting with Firefox 11, it's no longer supported to use the `withCredentials` attribute when performing synchronous requests. Attempting to do so throws an `NS_ERROR_DOM_INVALID_ACCESS_ERR` exception.

10

Internet Explorer versions 8 and 9 supported cross-domain requests (CORS) using [`XDomainRequest`](https://developer.mozilla.org/docs/Web/API/XDomainRequest).

12

4

≤37

18

4

Starting with Firefox 11, it's no longer supported to use the `withCredentials` attribute when performing synchronous requests. Attempting to do so throws an `NS_ERROR_DOM_INVALID_ACCESS_ERR` exception.

12

3.2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/withCredentials" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/withCredentials</a>
