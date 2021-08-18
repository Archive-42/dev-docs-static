XMLHttpRequestEventTarget.onload
================================

The `XMLHttpRequestEventTarget.onload` is the function called when an [`XMLHttpRequest`](../xmlhttprequest) transaction completes successfully.

Syntax
------

    XMLHttpRequest.onload = callback;

### Values

-   `callback` is the function to be executed when the request completes successfully. It receives a [`ProgressEvent`](../progressevent) object as its first argument. The value of *this* (i.e. the context) is the same [`XMLHttpRequest`](../xmlhttprequest) this callback is related to.

Example
-------

    var xmlhttp = new XMLHttpRequest(),
      method = 'GET',
      url = 'https://developer.mozilla.org/';

    xmlhttp.open(method, url, true);
    xmlhttp.onload = function () {
      // Do something with the retrieved data ( found in xmlhttp.response )
    };
    xmlhttp.send();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#handler-xhr-onload">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`onload`

Yes

≤18

Yes

9

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget/onload" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget/onload</a>
