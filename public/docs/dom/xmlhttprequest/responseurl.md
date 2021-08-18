XMLHttpRequest.responseURL
==========================

The read-only `XMLHttpRequest.responseURL` property returns the serialized URL of the response or the empty string if the URL is `null`. If the URL is returned, any URL fragment present in the URL will be stripped away. The value of `responseURL` will be the final URL obtained after any redirects.

Example
-------

    var xhr = new XMLHttpRequest();
    xhr.open('GET', 'http://example.com/test', true);
    xhr.onload = function () {
      console.log(xhr.responseURL); // http://example.com/test
    };
    xhr.send(null);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#the-responseurl-attribute">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`responseURL`

37

14

32

No

24

8

37

37

32

24

Yes

3.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseURL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseURL</a>
