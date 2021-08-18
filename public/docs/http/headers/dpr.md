DPR
===

**Secure context**  
This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#Browser_compatibility).

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Guidelines/Conventions_definitions#Experimental)**  
Check the [Browser compatibility table](#Browser_compatibility) carefully before using this in production.

The `DPR` header is a [Client Hints](https://developer.mozilla.org/en-US/docs/Glossary/Client_hints) headers which represents the client device pixel ratio ([DPR](https://developer.mozilla.org/en-US/docs/Glossary/DPR)), which is the the number of physical device pixels corresponding to every CSS pixel.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>?</td></tr></tbody></table>

**Note:** Client Hints are accessible only on secure origins (via TLS). Server has to opt in to receive `DPR` header from the client by sending [`Accept-CH`](accept-ch) and [`Accept-CH-Lifetime`](accept-ch-lifetime) response headers.

Syntax
------

    DPR: <number>

Examples
--------

Server first needs to opt in to receive `DPR` header by sending the response headers [`Accept-CH`](accept-ch) containing `DPR` and [`Accept-CH-Lifetime`](accept-ch-lifetime).

    Accept-CH: DPR
    Accept-CH-Lifetime: 86400

Then on subsequent requests the client might send `DPR` header back:

    DPR: 1.0

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`DPR`

46

≤79

?

?

33

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`DPR`

46

46

?

33

?

5.0

See also
--------

-   [`Accept-CH`](accept-ch)
-   [`Accept-CH-Lifetime`](accept-ch-lifetime)
-   [`Vary`](vary)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/DPR$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/DPR" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/DPR</a>
