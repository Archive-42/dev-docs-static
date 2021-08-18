CSP: require-sri-for
====================

**Obsolete**  
This feature is obsolete. Although it may still work in some browsers, its use is discouraged since it could be removed at any time. Try to avoid using it.

The [HTTP](../../index) [`Content-Security-Policy`](../content-security-policy) `require-sri-for` directive instructs the client to require the use of [Subresource Integrity](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity) for scripts or styles on the page.

Syntax
------

    Content-Security-Policy: require-sri-for script;
    Content-Security-Policy: require-sri-for style;
    Content-Security-Policy: require-sri-for script style;

`script`  
Requires [SRI](https://developer.mozilla.org/en-US/docs/Glossary/SRI) for scripts.

`style`  
Requires [SRI](https://developer.mozilla.org/en-US/docs/Glossary/SRI) for style sheets.

`script style`  
Requires [SRI](https://developer.mozilla.org/en-US/docs/Glossary/SRI) for both, scripts and style sheets.

Examples
--------

If you set your site to require SRI for script and styles using this directive:

    Content-Security-Policy: require-sri-for script style

[`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) elements like the following will be loaded as they use a valid integrity attribute.

    <script src="https://code.jquery.com/jquery-3.1.1.slim.js"
            integrity="sha256-5i/mQ300M779N2OVDrl16lbohwXNUdzL/R2aVUXyXWA="
            crossorigin="anonymous"></script>

However, scripts without integrity won't load anymore:

    <script src="https://code.jquery.com/jquery-3.1.1.slim.js"></script>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`require-sri-for`

54

79

49 — 68

Disabled

49 — 68

Disabled

Disabled From version 49 until version 68 (exclusive): this feature is behind the `security.csp.experimentalEnabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

41

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`require-sri-for`

54

54

49 — 68

Disabled

49 — 68

Disabled

Disabled From version 49 until version 68 (exclusive): this feature is behind the `security.csp.experimentalEnabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

41

No

6.0

See also
--------

-   [`Content-Security-Policy`](../content-security-policy)
-   [Subresource Integrity](https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/require-sri-for$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/require-sri-for" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/require-sri-for</a>
