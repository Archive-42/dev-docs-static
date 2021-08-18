Sec-Fetch-Mode
==============

**Draft**  
This page is not complete.

The `Sec-Fetch-Mode` fetch metadata header indicates the request's mode.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Fetch_Metadata_Request_Header">Fetch Metadata Request Header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes, since it has prefix <code>Sec-</code></td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_request_header">CORS-safelisted request header</a></td><td></td></tr></tbody></table>

Syntax
------

    Sec-Fetch-Mode: cors
    Sec-Fetch-Mode: navigate
    Sec-Fetch-Mode: nested-navigate
    Sec-Fetch-Mode: no-cors
    Sec-Fetch-Mode: same-origin
    Sec-Fetch-Mode: websocket

Values
------

`cors`

`navigate`

`nested-navigate`

`no-cors`

`same-origin`

`websocket`

Examples
--------

TODO

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-fetch-metadata/#sec-fetch-mode-header">Fetch Metadata Request Headers</a></td><td>The Sec-Fetch-Mode HTTP Request Header</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Sec-Fetch-Mode`

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

`Sec-Fetch-Mode`

76

76

No

54

No

No

See also
--------

-   [`Sec-Fetch-Site`](sec-fetch-site)
-   [`Sec-Fetch-User`](sec-fetch-user)
-   [`Sec-Fetch-Dest`](sec-fetch-dest)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-Fetch-Mode$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-Fetch-Mode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-Fetch-Mode</a>
