Access-Control-Allow-Methods
============================

The `Access-Control-Allow-Methods` response header specifies the method or methods allowed when accessing the resource in response to a [preflight request](https://developer.mozilla.org/en-US/docs/Glossary/preflight_request).

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Access-Control-Allow-Methods: <method>, <method>, ...
    Access-Control-Allow-Methods: *

Directives
----------

&lt;method&gt;  
Comma-delimited list of the allowed [HTTP request methods](../methods).

 `*` (wildcard)  
The value "`*`" only counts as a special wildcard value for requests without credentials (requests without [HTTP cookies](../cookies) or HTTP authentication information). In requests with credentials, it is treated as the literal method name "`*`" without special semantics.

Examples
--------

    Access-Control-Allow-Methods: POST, GET, OPTIONS
    Access-Control-Allow-Methods: *

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#http-access-control-allow-methods">Fetch<br />
<span class="small">The definition of 'Access-Control-Allow-Methods' in that specification.</span></a></td><td><span class="spec-Living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Access-Control-Allow-Methods`

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

`Access-Control-Allow-Methods`

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
-   [`Access-Control-Allow-Headers`](access-control-allow-headers)
-   [`Access-Control-Request-Method`](access-control-request-method)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Methods$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Methods" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Allow-Methods</a>
