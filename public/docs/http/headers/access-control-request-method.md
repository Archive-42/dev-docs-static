Access-Control-Request-Method
=============================

The `Access-Control-Request-Method` request header is used by browsers when issuing a [preflight request](https://developer.mozilla.org/en-US/docs/Glossary/preflight_request), to let the server know which [HTTP method](../methods) will be used when the actual request is made. This header is necessary as the preflight request is always an [`OPTIONS`](../methods/options) and doesn't use the same method as the actual request.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Access-Control-Request-Method: <method>

Directives
----------

&lt;method&gt;  
One of the [HTTP request methods](../methods), for example [`GET`](../methods/get), [`POST`](../methods/post), or [`DELETE`](../methods/delete).

Examples
--------

    Access-Control-Request-Method: POST

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#http-access-control-request-method">Fetch<br />
<span class="small">The definition of 'Access-Control-Request-Method' in that specification.</span></a></td><td><span class="spec-Living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Access-Control-Request-Method`

4

12

3.5

10

12

4

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Access-Control-Request-Method`

2

Yes

4

12

3.2

Yes

See also
--------

-   [`Access-Control-Request-Headers`](access-control-request-headers)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Request-Method$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Request-Method" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Access-Control-Request-Method</a>
