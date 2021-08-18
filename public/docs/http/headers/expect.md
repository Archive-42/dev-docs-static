Expect
======

The `Expect` HTTP request header indicates expectations that need to be fulfilled by the server in order to properly handle the request.

The only expectation defined in the specification is `Expect: 100-continue`, to which the server shall respond with:

-   [`100`](../status/100) if the information contained in the header is sufficient to cause an immediate success,
-   [`417`](../status/417) (Expectation Failed) if it cannot meet the expectation; or any other 4xx status otherwise.

For example, the server may reject a request if its [`Content-Length`](content-length) is too large.

No common browsers send the `Expect` header, but some other clients such as cURL do so by default.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

No other expectations except "100-continue" are specified currently.

    Expect: 100-continue

Directives
----------

100-continue  
Informs recipients that the client is about to send a (presumably large) message body in this request and wishes to receive a [`100`](../status/100) (Continue) interim response.

Examples
--------

### Large message body

A client sends a request with a Expect header and waits for the server to respond before sending the message body.

    PUT /somewhere/fun HTTP/1.1
    Host: origin.example.com
    Content-Type: video/h264
    Content-Length: 1234567890987
    Expect: 100-continue

The server now checks the request headers and may respond with a [`100`](../status/100) (Continue) response to instruct the client to go ahead and send the message body, or it will send a [`417`](../status/417) (Expectation Failed) status if any of the expectations cannot be met.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-5.1.1">RFC 7231, section 5.1.1: Expect</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Expect`

?

?

?

?

?

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Expect`

?

?

?

?

?

?

See also
--------

-   [`417`](../status/417)` Expectation Failed`
-   [`100`](../status/100)` Continue`

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Expect$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Expect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Expect</a>
