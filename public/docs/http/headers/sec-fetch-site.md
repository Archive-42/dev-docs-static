Sec-Fetch-Site
==============

**Draft**  
This page is not complete.

The `Sec-Fetch-Site` fetch metadata header indicates the relationship between a request initiator's origin and the origin of the resource.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Fetch_Metadata_Request_Header">Fetch Metadata Request Header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes, since it has prefix <code>Sec-</code></td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_response_header">CORS-safelisted response header</a></td><td></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_request_header">CORS-safelisted request header</a></td><td></td></tr></tbody></table>

Syntax
------

    Sec-Fetch-Site: cross-site
    Sec-Fetch-Site: same-origin
    Sec-Fetch-Site: same-site
    Sec-Fetch-Site: none

Values
------

`cross-site`  
`same-origin`  
`same-site`  
`none`  
This request does not relate to any context like site, origin, or frame. This can happen when user had initiated this request by, e.g. directly entering a URL in the address bar, opening a bookmark, or draging-and-dropping a file into the browser window.

Examples
--------

TODO

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-fetch-metadata/#sec-fetch-site-header">Fetch Metadata Request Headers</a></td><td>The Sec-Fetch-Site HTTP Request Header</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Sec-Fetch-Site`

76

79

No

No

63

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Sec-Fetch-Site`

76

76

No

54

No

No

See also
--------

-   [`Sec-Fetch-Mode`](sec-fetch-mode)
-   [`Sec-Fetch-User`](sec-fetch-user)
-   [`Sec-Fetch-Dest`](sec-fetch-dest)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-Fetch-Site$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-Fetch-Site" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-Fetch-Site</a>
