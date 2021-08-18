Cross-Origin-Resource-Policy
============================

**Note:** Due to a [bug in Chrome](https://bugs.chromium.org/p/chromium/issues/detail?id=1074261), setting Cross-Origin-Resource-Policy can break PDF rendering, preventing visitors from being able to read past the first page of some PDFs. Due to a [bug in Firefox](https://bugzilla.mozilla.org/show_bug.cgi?id=1638323), setting Cross-Origin-Resource-Policy can prevent some resources (such as PDFs) from being downloaded in some circumstances. Exercise caution using this header in a production environment.

The HTTP `Cross-Origin-Resource-Policy` response header conveys a desire that the browser blocks no-cors cross-origin/cross-site requests to the given resource.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Cross-Origin-Resource-Policy: same-site | same-origin | cross-origin

Examples
--------

The response header below will cause compatible user agents to disallow cross-origin no-cors requests:

    Cross-Origin-Resource-Policy: same-origin

For more examples, see <https://resourcepolicy.fyi/>.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#cross-origin-resource-policy-header">Fetch</a></td><td><span class="spec-Living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Cross-Origin-Resource-Policy`

73

 73   
Until version 75, downloads for files with this header would fail in Chrome. See [bug 952834](https://crbug.com/952834).

From version 80, linearized PDFs served inline with this header fail to render properly. See [bug 1074261](https://crbug.com/1074261).

79

74

74

69

Disabled

Disabled From version 69: this feature is behind the `browser.tabs.remote.useCORP` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

No

12

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Cross-Origin-Resource-Policy`

73

 73   
Until version 75, downloads for files with this header would fail in WebView. See [bug 952834](https://crbug.com/952834).

From version 80, linearized PDFs served inline with this header fail to render properly. See [bug 1074261](https://crbug.com/1074261).

73

 73   
Until version 75, downloads for files with this header would fail in Chrome. See [bug 952834](https://crbug.com/952834).

From version 80, linearized PDFs served inline with this header fail to render properly. See [bug 1074261](https://crbug.com/1074261).

No

No

12

No

See also
--------

-   [Cross-Origin Resource Policy (CORP) explainer](../cross-origin_resource_policy_(corp))
-   [Consider deploying Cross-Origin Resource Policy](https://resourcepolicy.fyi/)
-   [`Access-Control-Allow-Origin`](access-control-allow-origin)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Resource-Policy$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Resource-Policy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cross-Origin-Resource-Policy</a>
