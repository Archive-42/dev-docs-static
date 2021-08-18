Access-Control-Expose-Headers
=============================

The `Access-Control-Expose-Headers` response header indicates which headers can be exposed as part of the response by listing their names.

By default, only the 7 [CORS-safelisted response headers](https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_response_header) are exposed:

-   [`Cache-Control`](cache-control)
-   [`Content-Language`](content-language)
-   [`Content-Length`](content-length)
-   [`Content-Type`](content-type)
-   [`Expires`](expires)
-   [`Last-Modified`](last-modified)
-   [`Pragma`](pragma)

If you want clients to be able to access other headers, you have to list them using the `Access-Control-Expose-Headers` header. [`Content-Length`](content-length) was not part of the original set safelisted response headers \[[ref](https://github.com/whatwg/fetch/pull/626)\].

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Access-Control-Expose-Headers: <header-name>, <header-name>, ...
    Access-Control-Expose-Headers: *

Directives
----------

&lt;header-name&gt;  
A list of exposed headers consisting of zero or more [header names](../headers) other than the [CORS-safelisted request headers](https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_request_header) that the resource might use and can be exposed.

 `*` (wildcard)  
The value "`*`" only counts as a special wildcard value for requests without credentials (requests without [HTTP cookies](../cookies) or HTTP authentication information). In requests with credentials, it is treated as the literal header name "`*`" without special semantics.  
Note that the [`Authorization`](authorization) header can't be wildcarded and always needs to be listed explicitly.

Examples
--------

To expose a non-CORS-safelisted request header, you can specify:

    Access-Control-Expose-Headers: Content-Length

To additionally expose a custom header, like `X-Kuma-Revision`, you can specify multiple headers separated by a comma:

    Access-Control-Expose-Headers: Content-Length, X-Kuma-Revision

In requests without credentials, you can also use a wildcard value:

    Access-Control-Expose-Headers: *

However, this won't wildcard the [`Authorization`](authorization) header, so if you need to expose that, you will need to list it explicitly:

    Access-Control-Expose-Headers: *, Authorization

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#http-access-control-expose-headers">Fetch<br />
<span class="small">The definition of 'Access-Control-Expose-Headers' in that specification.</span></a></td><td><span class="spec-Living">Living Standard</span></td><td></td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Access-Control-Expose-Headers`

4

12

3.5

10

12

4

Wildcard (`*`)

65

79

69

No

52

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Access-Control-Expose-Headers`

2

Yes

4

12

3.2

Yes

Wildcard (`*`)

65

65

No

47

No

9.0

See also
--------

-   [`Access-Control-Allow-Headers`](access-control-allow-headers)
-   [`Access-Control-Allow-Origin`](access-control-allow-origin)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Expose-Headers$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Expose-Headers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Expose-Headers</a>
