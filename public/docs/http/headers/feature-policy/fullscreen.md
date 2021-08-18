Feature-Policy: fullscreen
==========================

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Guidelines/Conventions_definitions#Experimental)**  
Check the [Browser compatibility table](#Browser_compatibility) carefully before using this in production.

The HTTP [`Feature-Policy`](../feature-policy) header `fullscreen` directive controls whether the current document is allowed to use [`Element.requestFullScreen()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/requestFullScreen). When this policy is enabled, the returned [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) rejects with a [`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError).

By default, top-level documents and their same-origin child frames can request and enter fullscreen mode. This directive allows or prevents cross-origin frames from using fullscreen mode. This includes same-origin frames.

If both this directive (i.e. via the `allow` attribute) and the `allowfullscreen` attribute are present on an `<iframe>` element, this directive takes precedence. There was a bug whereby the `fullscreen` directive didn't work unless the `allowfullscreen` attribute was also present, but this has been fixed as of Firefox 80 ([bug 1608358](https://bugzilla.mozilla.org/show_bug.cgi?id=1608358)).

Syntax
------

    Feature-Policy: fullscreen <allowlist>;

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

The default value is `'self'`.

Examples
--------

### General example

SecureCorp Inc. wants to disable the Fullscreen API within all browsing contexts except for its own origin and those whose origin is `https://example.com`. It can do so by delivering the following HTTP response header to define a feature policy:

    Feature-Policy: fullscreen 'self' https://example.com

### With an &lt;iframe&gt; element

FastCorp Inc. wants to disable `fullscreen` for all cross-origin child frames, except for a specific &lt;iframe&gt;. It can do so by delivering the following HTTP response header to define a feature policy:

    Feature-Policy: fullscreen 'self'

Then include an [allow](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#Attributes) attribute on the `<iframe>` element:

    <iframe src="https://other.com/videoplayer" allow="fullscreen"></iframe>

iframe attributes can selectively enable features in certain frames, and not in others, even if those frames contain documents from the same origin.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-permissions-policy/">Permissions Policy</a></td><td><span class="spec-ED">Editor's Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://fullscreen.spec.whatwg.org/#feature-policy-integration">Fullscreen API<br />
<span class="small">The definition of 'Fullscreen' in that specification.</span></a></td><td><span class="spec-ED">Editor's Draft</span></td><td>Defines the <code>fullscreen</code> policy.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`fullscreen`

62

79

74

74

Before Firefox 80, applying `fullscreen` to an `<iframe>` (i.e. via the `allow` attribute) does not work unless the `allowfullscreen` attribute is also present.

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

49

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`fullscreen`

62

62

65

Disabled

65

Disabled

Disabled From version 65: this feature is behind the `dom.security.featurePolicy.header.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

46

No

8.0

See also
--------

-   [`Feature-Policy`](../feature-policy) header
-   [Feature Policy](../../feature_policy)
-   [Using Feature Policy](../../feature_policy/using_feature_policy)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/fullscreen$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/fullscreen" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/fullscreen</a>
