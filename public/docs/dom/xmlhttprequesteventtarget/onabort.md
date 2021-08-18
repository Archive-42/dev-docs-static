XMLHttpRequestEventTarget.onabort
=================================

The `XMLHttpRequestEventTarget.onabort` is the function called when an [`XMLHttpRequest`](../xmlhttprequest) transaction is aborted, such as when the [`XMLHttpRequest.abort()`](../xmlhttprequest/abort) function is called.

Syntax
------

    XMLHttpRequest.onabort = callback;

### Values

-   `callback` is the function to be executed when the transaction is aborted.

Example
-------

    var xmlhttp = new XMLHttpRequest(),
      method = 'GET',
      url = 'https://developer.mozilla.org/';

    xmlhttp.open(method, url, true);
    xmlhttp.onabort = function () {
      console.log('** The request was aborted');
    };
    xmlhttp.send();
    //..
    xmlhttp.abort(); // This will invoke our onabort handler above

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#handler-xhr-onabort">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`onabort`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget/onabort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget/onabort</a>
