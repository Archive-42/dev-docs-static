Access-Control-Allow-Headers
============================

The `Access-Control-Allow-Headers` response header is used in response to a [preflight request](https://developer.mozilla.org/en-US/docs/Glossary/preflight_request) which includes the [`Access-Control-Request-Headers`](access-control-request-headers) to indicate which HTTP headers can be used during the actual request.

This header is required if the request has an [`Access-Control-Request-Headers`](access-control-request-headers) header.

[CORS-safelisted request headers](https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_request_header) are always allowed and hence usually aren't listed in `Access-Control-Allow-Headers` (unless there is a need to circumvent the safelist [additional restrictions](https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_request_header#Additional_restrictions)).

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Access-Control-Allow-Headers: <header-name>[, <header-name>]*
    Access-Control-Allow-Headers: *

Directives
----------

`<header-name>`  
The name of a supported request header. The header may list any number of headers, separated by commas.

 `*` (wildcard)  
The value "`*`" only counts as a special wildcard value for requests without credentials (requests without [HTTP cookies](../cookies) or HTTP authentication information). In requests with credentials, it is treated as the literal header name "`*`" without special semantics. Note that the [`Authorization`](authorization) header can't be wildcarded and always needs to be listed explicitly.

Examples
--------

### A custom header

Here's an example of what an `Access-Control-Allow-Headers` header might look like. It indicates that a custom header named `X-Custom-Header` is supported by CORS requests to the server (in addition to the [CORS-safelisted request headers](https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_request_header)).

    Access-Control-Allow-Headers: X-Custom-Header

### Multiple headers

This example shows `Access-Control-Allow-Headers` when it specifies support for multiple headers.

    Access-Control-Allow-Headers: X-Custom-Header, Upgrade-Insecure-Requests

### Bypassing additional restrictions

Although [CORS-safelisted request headers](https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_request_header) are always allowed and don't usually need to be listed in `Access-Control-Allow-Headers`, listing them anyway will circumvent the [additional restrictions](https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_request_header#Additional_restrictions) that apply.

    Access-Control-Allow-Headers: Accept

### Example preflight request

Let's look at an example of a [preflight request](https://developer.mozilla.org/en-US/docs/Glossary/preflight_request) involving `Access-Control-Allow-Headers`.

#### Request

First, the request. The preflight request is an [`OPTIONS`](../methods/options) request that includes some combination of the three preflight request headers: [`Access-Control-Request-Method`](access-control-request-method), [`Access-Control-Request-Headers`](access-control-request-headers), and [`Origin`](origin).

The preflight request below tells the server that we want to send a CORS `GET` request that has the headers listed in [`Access-Control-Request-Headers`](access-control-request-headers) ([`Content-Type`](content-type) and `x-requested-with`).

    OPTIONS /resource/foo
    Access-Control-Request-Method: GET
    Access-Control-Request-Headers: Content-Type, x-requested-with
    Origin: https://foo.bar.org

#### Response

If the CORS request indicated by the preflight request is authorized, the server will respond to the preflight request with a message that indicates the allowed origin, methods and headers. Below we see that [`Access-Control-Allow-Headers`](access-control-allow-headers) includes the headers that were requested.

    HTTP/1.1 200 OK
    Content-Length: 0
    Connection: keep-alive
    Access-Control-Allow-Origin: https://foo.bar.org
    Access-Control-Allow-Methods: POST, GET, OPTIONS, DELETE
    Access-Control-Allow-Headers: Content-Type, x-requested-with
    Access-Control-Max-Age: 86400

If the requested method isn't supported, the server will respond with an error.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#http-access-control-allow-headers">Fetch<br />
<span class="small">The definition of 'Access-Control-Allow-Headers' in that specification.</span></a></td><td><span class="spec-Living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Access-Control-Allow-Headers`

4

12

3.5

10

12

4

Wildcard (`*`)

63

79

69

No

50

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Access-Control-Allow-Headers`

2

Yes

4

12

3.2

Yes

Wildcard (`*`)

63

63

No

46

No

8.2

See also
--------

-   [`Access-Control-Allow-Origin`](access-control-allow-origin)
-   [`Access-Control-Expose-Headers`](access-control-expose-headers)
-   [`Access-Control-Allow-Methods`](access-control-allow-methods)
-   [`Access-Control-Request-Headers`](access-control-request-headers)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Headers$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Headers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Headers</a>
