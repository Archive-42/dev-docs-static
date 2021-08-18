Cross-Origin Resource Policy (CORP)
===================================

**Cross-Origin Resource Policy** is a policy set by the [`Cross-Origin-Resource-Policy` HTTP header](headers/cross-origin-resource-policy) that lets web sites and applications opt in to protection against certain requests from other origins (such as those issued with elements like `<script>` and `<img>`), to mitigate speculative side-channel attacks, like [Spectre](https://en.wikipedia.org/wiki/Spectre_(security_vulnerability)), as well as Cross-Site Script Inclusion attacks.

CORP is an additional layer of protection beyond the default [same-origin policy](https://developer.mozilla.org/en-US/docs/Glossary/same-origin_policy). Cross-Origin Resource Policy complements [Cross-Origin Read Blocking](https://fetch.spec.whatwg.org/#corb) (CORB), which is a mechanism to prevent some cross-origin reads by default.

The policy is only effective for [no-cors](https://fetch.spec.whatwg.org/#concept-request-mode) requests, which are issued by default for CORS-safelisted methods/headers.

As this policy is expressed via a *[response header](https://developer.mozilla.org/en-US/docs/Glossary/Response_header)*, the actual request is not prevented—rather, the browser prevents the *result* from being leaked by stripping the response body.

History
-------

The concept was originally proposed in 2012 (as From-Origin), but [resurrected](https://github.com/whatwg/fetch/issues/687) in Q2 of 2018 and implemented in Safari and Chromium.

In early 2018, two side-channel hardware vulnerabilities known as *Meltdown* and *Spectre* were disclosed. These vulnerabilities allowed sensitive data disclosure due to a race condition which arose as part of speculative execution functionality, designed to improve performance.

In response, Chromium shipped [Cross-Origin Read Blocking](https://fetch.spec.whatwg.org/#corb), which automatically protects certain resources (of Content-Type HTML, JSON and XML) against cross-origin reads. If the application does not serve a [`no-sniff` directive](headers/x-content-type-options), Chromium will attempt to guess the Content-Type and apply the protection anyway.

Cross-Origin Resource Policy is an opt-in response header which can protect *any* resource; there is no need for browsers to sniff MIME types.

Usage
-----

**Note:** Due to a [bug in Chrome](https://bugs.chromium.org/p/chromium/issues/detail?id=1074261), setting Cross-Origin-Resource-Policy can break PDF rendering, preventing visitors from being able to read past the first page of some PDFs. Exercise caution using this header in a production environment.

Web applications set a Cross-Origin Resource Policy via the [`Cross-Origin-Resource-Policy`](headers/cross-origin-resource-policy) HTTP response header, which accepts one of three values:

same-site  
Only requests from the same *[Site](https://developer.mozilla.org/en-US/docs/Glossary/Site)* can read the resource.

**Warning:** This is less secure than an [origin](https://developer.mozilla.org/en-US/docs/Glossary/origin). The [algorithm for checking if two origins are same site](https://html.spec.whatwg.org/multipage/origin.html#same-site) is defined in the HTML standard and involves checking the *registrable domain*.

same-origin  
Only requests from the same *[origin](https://developer.mozilla.org/en-US/docs/Glossary/origin)* (i.e. scheme + host + port) can read the resource.

cross-origin  
Requests from any *[origin](https://developer.mozilla.org/en-US/docs/Glossary/origin)* (both same-site and cross-site) can read the resource.

<!-- -->

    Cross-Origin-Resource-Policy: same-site | same-origin | cross-origin

During a cross-origin resource policy check, if the header is set, the browser will deny `no-cors` requests issued from a different origin/site.

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

[`Cross-Origin-Resource-Policy`](headers/cross-origin-resource-policy)

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

[`Cross-Origin-Resource-Policy`](headers/cross-origin-resource-policy)

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#cross-origin-resource-policy-header">Fetch</a></td><td><span class="spec-Living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

See also
--------

-   [`Cross-Origin-Resource-Policy`](headers/cross-origin-resource-policy) HTTP Header
-   [Bugzilla bug 1459573](https://bugzilla.mozilla.org/show_bug.cgi?id=1459573)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Cross-Origin_Resource_Policy_(CORP)$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Cross-Origin_Resource_Policy_(CORP)" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Cross-Origin_Resource_Policy_(CORP)</a>
