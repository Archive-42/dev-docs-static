Accept-CH
=========

**Secure context**  
This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#Browser_compatibility).

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Guidelines/Conventions_definitions#Experimental)**  
Check the [Browser compatibility table](#Browser_compatibility) carefully before using this in production.

The `Accept-CH` header is set by the server to specify which [Client Hints](https://developer.mozilla.org/en-US/docs/Glossary/Client_hints) headers a client should include in subsequent requests.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>?</td></tr></tbody></table>

**Note:** Client Hints are accessible only on secure origins (via TLS). Accept-CH and Accept-CH-Lifetime headers should be persisted for all secure requests to ensure Client Hints are sent reliably.

Syntax
------

    Accept-CH: <list of client hints>

Examples
--------

    Accept-CH: DPR, Viewport-Width
    Accept-CH: Width
    Accept-CH-Lifetime: 86400
    Vary: DPR, Viewport-Width, Width

**Note:** Remember to [vary the response](https://developer.mozilla.org/en-US/docs/Glossary/Client_hints#Varying_Client_Hints) based on the accepted client hints.

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Accept-CH`

46

≤79

?

?

33

?

`DPR`

46

≤79

?

?

33

?

`Viewport-Width`

46

≤79

?

?

33

?

`Width`

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

`Accept-CH`

46

46

?

33

?

5.0

`DPR`

46

46

?

33

?

5.0

`Viewport-Width`

46

46

?

33

?

5.0

`Width`

46

46

?

33

?

5.0

See also
--------

-   [`Accept-CH-Lifetime`](accept-ch-lifetime)
-   [`Vary`](vary)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-CH$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-CH" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-CH</a>
