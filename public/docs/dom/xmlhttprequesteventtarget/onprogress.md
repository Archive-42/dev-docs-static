XMLHttpRequestEventTarget.onprogress
====================================

The `XMLHttpRequestEventTarget.onprogress` is the function called periodically with information when an [`XMLHttpRequest`](../xmlhttprequest) before success completely.

Syntax
------

    XMLHttpRequest.onprogress = callback;

### Values

-   `callback` is the function to be called periodically before the request is completed.

### Event

-   *`event.loaded`* the amount of data currently transfered.
-   *`event.total`* the total amount of data to be transferred.

<!-- -->

    XMLHttpRequest.onprogress = function (event) {
      event.loaded;
      event.total;
    };

Example
-------

    var xmlhttp = new XMLHttpRequest(),
      method = 'GET',
      url = 'https://developer.mozilla.org/';

    xmlhttp.open(method, url, true);
    xmlhttp.onprogress = function () {
      //do something
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

`onprogress`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget/onprogress" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestEventTarget/onprogress</a>
