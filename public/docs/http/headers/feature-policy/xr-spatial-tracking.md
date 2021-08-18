Feature-Policy: xr-spatial-tracking
===================================

**Draft**  
This page is not complete.

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Guidelines/Conventions_definitions#Experimental)**  
Check the [Browser compatibility table](#Browser_compatibility) carefully before using this in production.

The HTTP [`Feature-Policy`](../feature-policy) header `xr-spatial-tracking` directive controls whether the current document is allowed to use the [WebXR Device API](https://developer.mozilla.org/en-US/docs/Web/API/WebXR_Device_API). This policy controls whether [`navigator.xr.requestSession()`](https://developer.mozilla.org/en-US/docs/Web/API/XR/requestSession) can return [`XRSession`](https://developer.mozilla.org/en-US/docs/Web/API/XRSession) that requires spatial tracking and whether user agent can indicate support for sessions supporting spatial tracking via [`navigator.xr.isSessionSupported()`](https://developer.mozilla.org/en-US/docs/Web/API/XR/isSessionSupported) and `devicechange` event on [`navigator.xr`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/xr) object.

Syntax
------

    Feature-Policy: xr-spatial-tracking <allowlist>;

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

The default allowlist is `'self'`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#permissions-policy">WebXR Device API<br />
<span class="small">The definition of 'Permissions Policy' in that specification.</span></a></td><td><span class="spec-WD">Working Draft</span></td><td></td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`xr-spatial-tracking`

79

79

No

No

66

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`xr-spatial-tracking`

No

79

No

No

No

No

See also
--------

-   [WebXR Device API](https://developer.mozilla.org/en-US/docs/Web/API/WebXR_Device_API)
-   [`navigator.xr.requestSession()`](https://developer.mozilla.org/en-US/docs/Web/API/XR/requestSession), and [`navigator.xr.isSessionSupported()`](https://developer.mozilla.org/en-US/docs/Web/API/XR/isSessionSupported) and `devicechange` event on [`navigator.xr`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/xr)
-   [`Feature-Policy`](../feature-policy) header
-   [Feature Policy](../../feature_policy)
-   [Using Feature Policy](../../feature_policy/using_feature_policy)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/xr-spatial-tracking$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/xr-spatial-tracking" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/xr-spatial-tracking</a>
