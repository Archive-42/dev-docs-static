Sec-Fetch-Dest
==============

**Draft**  
This page is not complete.

The `Sec-Fetch-Dest` fetch metadata header indicates the request's destination, that is how the fetched data will be used.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Fetch_Metadata_Request_Header">Fetch Metadata Request Header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes, since it has prefix <code>Sec-</code></td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_request_header">CORS-safelisted request header</a></td><td></td></tr></tbody></table>

Syntax
------

    Sec-Fetch-Dest: audio
    Sec-Fetch-Dest: audioworklet
    Sec-Fetch-Dest: document
    Sec-Fetch-Dest: embed
    Sec-Fetch-Dest: empty
    Sec-Fetch-Dest: font
    Sec-Fetch-Dest: image
    Sec-Fetch-Dest: manifest
    Sec-Fetch-Dest: nested-document
    Sec-Fetch-Dest: object
    Sec-Fetch-Dest: paintworklet
    Sec-Fetch-Dest: report
    Sec-Fetch-Dest: script
    Sec-Fetch-Dest: serviceworker
    Sec-Fetch-Dest: sharedworker
    Sec-Fetch-Dest: style
    Sec-Fetch-Dest: track
    Sec-Fetch-Dest: video
    Sec-Fetch-Dest: worker
    Sec-Fetch-Dest: xslt
    Sec-Fetch-Dest: audioworklet
    Sec-Fetch-Dest: audioworklet

Values
------

`audio`

`audioworklet`

`document`

`embed`

`empty`

`font`

`image`

`manifest`

`object`

`paintworklet`

`report`

`script`

`serviceworker`

`sharedworker`

`style`

`track`

`video`

`worker`

`xslt`

`nested-document`

Examples
--------

TODO

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-fetch-metadata/#sec-fetch-dest-header">Fetch Metadata Request Headers</a></td><td>The Sec-Fetch-Dest HTTP Request Header</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Sec-Fetch-Dest`

80

80

No

No

67

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Sec-Fetch-Dest`

80

80

No

No

No

No

See also
--------

-   [`Sec-Fetch-Mode`](sec-fetch-mode)
-   [`Sec-Fetch-Site`](sec-fetch-site)
-   [`Sec-Fetch-User`](sec-fetch-user)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-Fetch-Dest$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-Fetch-Dest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-Fetch-Dest</a>
