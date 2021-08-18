Feature-Policy: unsized-media
=============================

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Guidelines/Conventions_definitions#Experimental)**  
Check the [Browser compatibility table](#Browser_compatibility) carefully before using this in production.

The HTTP [`Feature-Policy`](../feature-policy) header `unsized-media` directive controls whether the current document is allowed to change the size of media elements after the initial layout is complete.

This restriction solves "layout instability" problem caused by providing default dimensions for images whose size is not specified in advance so that image doesn't change size after loading.

Syntax
------

    Feature-Policy: unsized-media <allowlist>;

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

Default value
-------------

The default value for unsized-media is `'*'`, that is unsized media elements are allowed for all origins by default. The page will re-flow every time an image with unknown dimensions is loaded.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-permissions-policy/">Permissions Policy</a></td><td><span class="spec-ED">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`unsized-media`

66

Disabled

66

Disabled

Disabled From version 66: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

79

Disabled

79

Disabled

Disabled From version 79: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

No

53

Disabled

53

Disabled

Disabled From version 53: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`unsized-media`

No

66

Disabled

66

Disabled

Disabled From version 66: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

47

Disabled

47

Disabled

Disabled From version 47: this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`).

No

9.0

See also
--------

-   [`Feature-Policy`](../feature-policy) header
-   [Feature Policy](../../feature_policy)
-   [Using Feature Policy](../../feature_policy/using_feature_policy)
-   [Proposal](https://github.com/w3c/webappsec-feature-policy/blob/master/policies/unsized-media.md)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/unsized-media$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/unsized-media" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/unsized-media</a>
