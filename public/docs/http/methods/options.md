OPTIONS
=======

The `OPTIONS` requests permitted communication options for a given URL or server. A client can specify a URL with this method, or an asterisk (`*`) to refer to the entire server.

<table><tbody><tr class="odd"><td>Request has body</td><td>No</td></tr><tr class="even"><td>Successful response has body</td><td>Yes</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Safe">Safe</a></td><td>Yes</td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Idempotent">Idempotent</a></td><td>Yes</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Cacheable">Cacheable</a></td><td>No</td></tr><tr class="even"><td>Allowed in HTML forms</td><td>No</td></tr></tbody></table>

Syntax
------

    OPTIONS /index.html HTTP/1.1
    OPTIONS * HTTP/1.1

Examples
--------

### Identifying allowed request methods

To find out which request methods a server supports, one can use the `curl` command-line program to issue an `OPTIONS` request:

    curl -X OPTIONS https://example.org -i

The response then contains an [`Allow`](../headers/allow) header that holds the allowed methods:

    HTTP/1.1 204 No Content
    Allow: OPTIONS, GET, HEAD, POST
    Cache-Control: max-age=604800
    Date: Thu, 13 Oct 2016 11:45:00 GMT
    Server: EOS (lax004/2813)

### Preflighted requests in CORS

In [CORS](../cors), a [preflight request](https://developer.mozilla.org/en-US/docs/Glossary/Preflight_request) is sent with the `OPTIONS` method so that the server can respond if it is acceptable to send the request. In this example, we will request permission for these parameters:

-   The [`Access-Control-Request-Method`](../headers/access-control-request-method) header sent in the preflight request tells the server that when the actual request is sent, it will have a [`POST`](post) request method.
-   The [`Access-Control-Request-Headers`](../headers/access-control-request-headers) header tells the server that when the actual request is sent, it will have the `X-PINGOTHER` and `Content-Type` headers.

<!-- -->

    OPTIONS /resources/post-here/ HTTP/1.1
    Host: bar.example
    Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
    Accept-Language: en-us,en;q=0.5
    Accept-Encoding: gzip,deflate
    Connection: keep-alive
    Origin: https://foo.example
    Access-Control-Request-Method: POST
    Access-Control-Request-Headers: X-PINGOTHER, Content-Type

The server now can respond if it will accept a request under these circumstances. In this example, the server response says that:

[`Access-Control-Allow-Origin`](../headers/access-control-allow-origin)  
The `https://foo.example` origin is permitted to request the `bar.example/resources/post-here/` URL via the following:

[`Access-Control-Allow-Methods`](../headers/access-control-allow-methods)  
[`POST`](post), [`GET`](get), and `OPTIONS` are permitted methods for the URL. (This header is similar to the [`Allow`](../headers/allow) response header, but used only for [CORS](../cors).)

[`Access-Control-Allow-Headers`](../headers/access-control-allow-headers)  
Any script inspecting the response is permitted to read the values of the `X-PINGOTHER` and `Content-Type` headers.

[`Access-Control-Max-Age`](../headers/access-control-max-age)  
The above permissions may be cached for 86,400 seconds (1 day).

<!-- -->

    HTTP/1.1 204 No Content
    Date: Mon, 01 Dec 2008 01:15:39 GMT
    Server: Apache/2.0.61 (Unix)
    Access-Control-Allow-Origin: https://foo.example
    Access-Control-Allow-Methods: POST, GET, OPTIONS
    Access-Control-Allow-Headers: X-PINGOTHER, Content-Type
    Access-Control-Max-Age: 86400
    Vary: Accept-Encoding, Origin
    Keep-Alive: timeout=2, max=100
    Connection: Keep-Alive

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-4.3.7">RFC 7231, section 4.3.7: OPTIONS</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`OPTIONS`

Yes

12

Yes

Yes

Yes

Yes

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`OPTIONS`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Allow`](../headers/allow) header
-   [CORS](../cors)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/OPTIONS$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/OPTIONS" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/OPTIONS</a>
