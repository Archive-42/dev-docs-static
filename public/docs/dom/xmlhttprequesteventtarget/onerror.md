XMLHttpRequestEventTarget.onerror
=================================

The `XMLHttpRequestEventTarget.onerror` is the function called when an [`XMLHttpRequest`](../xmlhttprequest) transaction fails due to an error.

It's important to note that this is only called if there's an error at the *network* level. If the error only exists at the *application* level (e.g. an HTTP error code is sent), this method will not be called.

Syntax
------

    XMLHttpRequest.onerror = callback;

### Values

-   `callback` is the function to be executed when the request fails.

Example
-------

    var xmlhttp = new XMLHttpRequest(),
      method = 'GET',
      url = 'https://developer.mozilla.org/';

    xmlhttp.open(method, url, true);
    xmlhttp.onerror = function () {
      console.log("** An error occurred during the transaction");
    };
    xmlhttp.send();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#handler-xhr-onerror">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`onerror`

Yes

≤18

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget/onerror" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget/onerror</a>
