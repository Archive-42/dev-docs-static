CSP: referrer
=============

**Deprecated**  
This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#Browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The HTTP [`Content-Security-Policy`](../content-security-policy) (CSP) `referrer` directive used to specify information in the [`Referer`](../referer) header (with a single `r` as this was a typo in the original spec) for links away from a page. This API is deprecated and removed from browsers.

Use the [`Referrer-Policy`](../referrer-policy) header instead.

Syntax
------

    Content-Security-Policy: referrer <referrer-policy>;

where `<referrer-policy>` can be one of the following values:

"no-referrer"  
The [`Referer`](../referer) header will be omitted entirely. No referrer information is sent along with requests.

"none-when-downgrade"  
This is the user agent's default behavior if no policy is specified. The origin is sent as referrer to a-priori as-much-secure destination (HTTPS-&gt;HTTPS), but isn't sent to a less secure destination (HTTPS-&gt;HTTP).

"origin"  
Only send the origin of the document as the referrer in all cases.  
The document `https://example.com/page.html` will send the referrer `https://example.com/`.

"origin-when-cross-origin" / "origin-when-crossorigin"  
Send a full URL when performing a same-origin request, but only send the origin of the document for other cases.

"unsafe-url"  
Send a full URL (stripped from parameters) when performing a same-origin or cross-origin request. This policy will leak origins and paths from TLS-protected resources to insecure origins. Carefully consider the impact of this setting.

Examples
--------

    Content-Security-Policy: referrer "none";

Specifications
--------------

Not part of any specification.

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`referrer`

33 — 56

No

37 — 62

No

? — 43

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`referrer`

4.4.3 — 56

33 — 56

37 — 62

? — 43

No

2.0 — 6.0

See also
--------

-   [`Content-Security-Policy`](../content-security-policy)
-   [`Referrer-Policy`](../referrer-policy) header
-   [`Referer`](../referer) header

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/referrer$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/referrer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/referrer</a>
