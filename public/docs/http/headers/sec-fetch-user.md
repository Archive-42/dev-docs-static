Sec-Fetch-User
==============

**Draft**  
This page is not complete.

The `Sec-Fetch-User` fetch metadata header indicates whether or not a navigation request was triggered by a user activation.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Fetch_Metadata_Request_Header">Fetch Metadata Request Header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes, since it has prefix <code>Sec-</code></td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_request_header">CORS-safelisted request header</a></td><td></td></tr></tbody></table>

Syntax
------

    Sec-Fetch-User: ?0
    Sec-Fetch-User: ?1

Values
------

The value is a Boolean Structured Header.

`?0`  
The navigation request was triggered by a user activation.

`?1`  
The navigation request was triggered by something other than a user activation.

Examples
--------

TODO

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-fetch-metadata/#sec-fetch-user-header">Fetch Metadata Request Headers</a></td><td>The Sec-Fetch-User HTTP Request Header</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Sec-Fetch-User`

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

`Sec-Fetch-User`

76

76

No

54

No

No

See also
--------

-   [`Sec-Fetch-Dest`](sec-fetch-dest)
-   [`Sec-Fetch-Mode`](sec-fetch-mode)
-   [`Sec-Fetch-Site`](sec-fetch-site)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-Fetch-User$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-Fetch-User" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-Fetch-User</a>
