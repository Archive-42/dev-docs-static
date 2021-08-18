Device-Memory
=============

**Secure context**  
This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#Browser_compatibility).

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Guidelines/Conventions_definitions#Experimental)**  
Check the [Browser compatibility table](#Browser_compatibility) carefully before using this in production.

The `Device-Memory` header is a [Device Memory API](https://developer.mozilla.org/en-US/docs/Web/API/Device_Memory_API) header that works like [Client Hints](https://developer.mozilla.org/en-US/docs/Glossary/Client_hints) header which represents the approximate amount of RAM client device has.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>?</td></tr></tbody></table>

**Note:** Client Hints are accessible only on secure origins (via TLS). Server has to opt in to receive `Device-Memory` header from the client by sending [`Accept-CH`](accept-ch) and [`Accept-CH-Lifetime`](accept-ch-lifetime) response headers.

Syntax
------

The amount of device RAM can be used as a fingerprinting variable, so values for the header are intentionally coarse to reduce the potential for its misuse. The header takes on the following values: `0.25`, `0.5`, `1`, `2`, `4`, `8`.

    Device-Memory: <number>

Examples
--------

Server first needs to opt in to receive `Device-Memory` header by sending the response headers [`Accept-CH`](accept-ch) containing `Device-Memory` and [`Accept-CH-Lifetime`](accept-ch-lifetime).

    Accept-CH: Device-Memory
    Accept-CH-Lifetime: 86400

Then on subsequent requests the client might send `Device-Memory` header back:

    Device-Memory: 1

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/device-memory/#sec-device-memory-client-hint-header">Device Memory 1<br />
<span class="small">The definition of 'Device-Memory' in that specification.</span></a></td><td><span class="spec-ED">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Device-Memory`

61

≤79

?

?

48

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Device-Memory`

61

61

?

?

?

8.0

See also
--------

-   [Device Memory API](https://developer.mozilla.org/en-US/docs/Web/API/Device_Memory_API)
-   [`Accept-CH`](accept-ch)
-   [`Accept-CH-Lifetime`](accept-ch-lifetime)
-   [`Vary`](vary)
-   [`Navigator.deviceMemory`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/deviceMemory)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Device-Memory$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Device-Memory" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Device-Memory</a>
