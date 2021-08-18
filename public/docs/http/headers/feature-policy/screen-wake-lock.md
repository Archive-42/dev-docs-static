Feature-Policy: screen-wake-lock
================================

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Guidelines/Conventions_definitions#Experimental)**  
Check the [Browser compatibility table](#Browser_compatibility) carefully before using this in production.

The HTTP [`Feature-Policy`](../feature-policy) header `screen-wake-lock` directive controls whether the current document is allowed to use [Screen Wake Lock API](https://developer.mozilla.org/en-US/docs/Web/API/Screen_Wake_Lock_API) to indicate that device should not dim or turn off the screen.

**Note:** In earlier specification drafts this directive was called [`wake-lock`](wake-lock).

Syntax
------

    Feature-Policy: screen-wake-lock <allowlist>;

&lt;allowlist&gt;  
An `allowlist` is a list of origins that takes one or more of the following values, separated by spaces:

-   `*`: The feature will be allowed in this document, and all nested browsing contexts (iframes) regardless of their origin.
-   `'self'`: The feature will be allowed in this document, and in all nested browsing contexts (iframes) in the same origin.
-   `'src'`: (In an iframe `allow` attribute only) The feature will be allowed in this iframe, as long as the document loaded into it comes from the same origin as the URL in the iframe's [src](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#Attributes) attribute.
    The `'src'` origin is used in the iframe `allow` attribute only, and is the *default* `allowlist` value.

-   `'none'`: The feature is disabled in top-level and nested browsing contexts.
-   &lt;origin(s)&gt;: The feature is allowed for specific origins (for example, https://example.com). Origins should be separated by a space.

The values `*` (enable for all origins) or `'none'` (disable for all origins) may only be used alone, while `'self'` and `'src'` may be used with one or more origins.

Features are each defined to have a default allowlist, which is one of:

-   `*`: The feature is allowed by default in top-level browsing contexts and all nested browsing contexts (iframes).
-   `'self'`: The feature is allowed by default in top-level browsing contexts and in nested browsing contexts (iframes) in the same origin. The feature is not allowed in cross-origin documents in nested browsing contexts.
-   `'none'`: The feature is disabled in top-level and nested browsing contexts.

Default policy
--------------

Default allow list for `screen-wake-lock` is `'self'`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-permissions-policy/">Permissions Policy</a></td><td><span class="spec-ED">Editor's Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://w3c.github.io/screen-wake-lock/#the-screen-wake-lock-powerful-feature">Screen Wake Lock API</a></td><td>Editor's Draft</td><td>Initial definition of <code>screen-wake-lock</code> feature directive.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found. Please contribute data for "http.headers.Feature-Policy.screen-wake-lock" (depth: 1) to the [MDN compatibility data repository](https://github.com/mdn/browser-compat-data).

See also
--------

-   [Screen Wake Lock API](https://developer.mozilla.org/en-US/docs/Web/API/Screen_Wake_Lock_API)
-   [`Feature-Policy`](../feature-policy) header
-   [Feature Policy](../../feature_policy)
-   [Using Feature Policy](../../feature_policy/using_feature_policy)
-   [Default value of the allow list](https://www.w3.org/TR/wake-lock/#wake-locks)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/screen-wake-lock$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/screen-wake-lock" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/screen-wake-lock</a>
