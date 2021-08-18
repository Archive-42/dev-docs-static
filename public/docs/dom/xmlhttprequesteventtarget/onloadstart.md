XMLHttpRequestEventTarget.onloadstart
=====================================

The `XMLHttpRequestEventTarget.onloadstart` is the function called when an [`XMLHttpRequest`](../xmlhttprequest) transaction starts transferring data.

Syntax
------

    XMLHttpRequest.onloadstart = callback;

### Values

-   `callback` is the function to be called when the transaction begins to transfer data.

Example
-------

    var xmlhttp = new XMLHttpRequest(),
      method = 'GET',
      url = 'https://developer.mozilla.org/';

    xmlhttp.open(method, url, true);
    xmlhttp.onloadstart = function () {
      console.log("Download underway");
    };
    xmlhttp.send();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#handler-xhr-onloadstart">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`onloadstart`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget/onloadstart" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget/onloadstart</a>
