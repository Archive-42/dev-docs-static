CSP: block-all-mixed-content
============================

The HTTP [`Content-Security-Policy`](../content-security-policy) (CSP) `block-all-mixed-content` directive prevents loading any assets over HTTP when the page uses HTTPS.

All [mixed content](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content) resource requests are blocked, including both active and passive mixed content. This also applies to [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) documents, ensuring the entire page is mixed content-free.

The [`upgrade-insecure-requests`](upgrade-insecure-requests) directive is evaluated before `block-all-mixed-content`. If the former is set, the latter does nothing, so set one directive or the other – not both, unless you want to force HTTPS on older browsers that do not force it after a redirect to HTTP.

Syntax
------

    Content-Security-Policy: block-all-mixed-content;

Examples
--------

    Content-Security-Policy: block-all-mixed-content;

    <meta http-equiv="Content-Security-Policy" content="block-all-mixed-content">

To disallow http assets on a more granular level, you can also set individual directives to `https:`. For example, to disallow nonsecure HTTP images:

    Content-Security-Policy: img-src https:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-mixed-content/#block-all-mixed-content">Mixed Content<br />
<span class="small">The definition of 'block-all-mixed-content' in that specification.</span></a></td><td><span class="spec-CR">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`block-all-mixed-content`

Yes

≤79

48

No

Yes

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`block-all-mixed-content`

Yes

Yes

48

?

?

Yes

See also
--------

-   [`Content-Security-Policy`](../content-security-policy)
-   [`upgrade-insecure-requests`](upgrade-insecure-requests)
-   [Mixed content](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/block-all-mixed-content$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/block-all-mixed-content" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/block-all-mixed-content</a>
