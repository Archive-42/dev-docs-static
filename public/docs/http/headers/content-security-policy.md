Content-Security-Policy
=======================

The HTTP `Content-Security-Policy` response header allows web site administrators to control resources the user agent is allowed to load for a given page. With a few exceptions, policies mostly involve specifying server origins and script endpoints. This helps guard against cross-site scripting attacks ([XSS](https://developer.mozilla.org/en-US/docs/Glossary/XSS)).

For more information, see the introductory article on [Content Security Policy (CSP)](../csp).

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Content-Security-Policy: <policy-directive>; <policy-directive>

where `<policy-directive>` consists of: `<directive> <value>` with no internal punctuation.

Directives
----------

### Fetch directives

Fetch directives control the locations from which certain resource types may be loaded.

[`child-src`](content-security-policy/child-src)  
Defines the valid sources for [web workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API) and nested browsing contexts loaded using elements such as [`<frame>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame) and [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe).

Instead of `child-src`, if you want to regulate nested browsing contexts and workers, you should use the [`frame-src`](content-security-policy/frame-src) and [`worker-src`](content-security-policy/worker-src) directives, respectively.

[`connect-src`](content-security-policy/connect-src)  
Restricts the URLs which can be loaded using script interfaces

[`default-src`](content-security-policy/default-src)  
Serves as a fallback for the other [fetch directives](https://developer.mozilla.org/en-US/docs/Glossary/Fetch_directive).

[`font-src`](content-security-policy/font-src)  
Specifies valid sources for fonts loaded using [`@font-face`](https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face).

[`frame-src`](content-security-policy/frame-src)  
Specifies valid sources for nested browsing contexts loading using elements such as [`<frame>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame) and [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe).

[`img-src`](content-security-policy/img-src)  
Specifies valid sources of images and favicons.

[`manifest-src`](content-security-policy/manifest-src)  
Specifies valid sources of application manifest files.

[`media-src`](content-security-policy/media-src)  
Specifies valid sources for loading media using the [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) , [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) and [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track) elements.

[`object-src`](content-security-policy/object-src)  
Specifies valid sources for the [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object), [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed), and [`<applet>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/applet) elements.

Elements controlled by `object-src` are perhaps coincidentally considered legacy HTML elements and are not receiving new standardized features (such as the security attributes `sandbox` or `allow` for `<iframe>`). Therefore it is **recommended** to restrict this fetch-directive (e.g., explicitly set `object-src 'none'` if possible).

 [`prefetch-src`](content-security-policy/prefetch-src)   
Specifies valid sources to be prefetched or prerendered.

[`script-src`](content-security-policy/script-src)  
Specifies valid sources for JavaScript.

 [`script-src-elem`](content-security-policy/script-src-elem)   
Specifies valid sources for JavaScript [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) elements.

 [`script-src-attr`](content-security-policy/script-src-attr)   
Specifies valid sources for JavaScript inline event handlers.

<!-- -->

[`style-src`](content-security-policy/style-src)  
Specifies valid sources for stylesheets.

 [`style-src-elem`](content-security-policy/style-src-elem)   
Specifies valid sources for stylesheets [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) elements and [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) elements with `rel="stylesheet"`.

 [`style-src-attr`](content-security-policy/style-src-attr)   
Specifies valid sources for inline styles applied to individual DOM elements.

 [`worker-src`](content-security-policy/worker-src)   
Specifies valid sources for [`Worker`](https://developer.mozilla.org/en-US/docs/Web/API/Worker), [`SharedWorker`](https://developer.mozilla.org/en-US/docs/Web/API/SharedWorker), or [`ServiceWorker`](https://developer.mozilla.org/en-US/docs/Web/API/ServiceWorker) scripts.

### Document directives

Document directives govern the properties of a document or [worker](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API) environment to which a policy applies.

[`base-uri`](content-security-policy/base-uri)  
Restricts the URLs which can be used in a document's [`<base>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/base) element.

[`plugin-types`](content-security-policy/plugin-types)  
Restricts the set of plugins that can be embedded into a document by limiting the types of resources which can be loaded.

[`sandbox`](content-security-policy/sandbox)  
Enables a sandbox for the requested resource similar to the [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) `sandbox` attribute.

### Navigation directives

Navigation directives govern to which locations a user can navigate or submit a form, for example.

[`form-action`](content-security-policy/form-action)  
Restricts the URLs which can be used as the target of a form submissions from a given context.

[`frame-ancestors`](content-security-policy/frame-ancestors)  
Specifies valid parents that may embed a page using [`<frame>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame), [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe), [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object), [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed), or [`<applet>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/applet).

 [`navigate-to`](content-security-policy/navigate-to)   
Restricts the URLs to which a document can initiate navigation by any means, including [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) (if [`form-action`](content-security-policy/form-action) is not specified), [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a), [`window.location`](https://developer.mozilla.org/en-US/docs/Web/API/Window/location), [`window.open`](https://developer.mozilla.org/en-US/docs/Web/API/Window/open), etc.

### Reporting directives

Reporting directives control the reporting process of CSP violations. See also the [`Content-Security-Policy-Report-Only`](content-security-policy-report-only) header.

 [`report-uri`](content-security-policy/report-uri)   
Instructs the user agent to report attempts to violate the Content Security Policy. These violation reports consist of [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON) documents sent via an HTTP `POST` request to the specified URI.

Though the [`report-to`](content-security-policy/report-to) directive is intended to replace the deprecated `report-uri` directive, [`report-to`](content-security-policy/report-to) is not supported in most browsers yet. So for compatibility with current browsers while also adding forward compatibility when browsers get [`report-to`](content-security-policy/report-to) support, you can specify both `report-uri` and [`report-to`](content-security-policy/report-to):

    Content-Security-Policy: ...; report-uri https://endpoint.example.com; report-to groupname

In browsers that support [`report-to`](content-security-policy/report-to), the `report-uri` directive will be ignored.

 [`report-to`](content-security-policy/report-to)   
Fires a `SecurityPolicyViolationEvent`.

### Other directives

[`block-all-mixed-content`](content-security-policy/block-all-mixed-content)  
Prevents loading any assets using HTTP when the page is loaded using HTTPS.

 [`referrer`](content-security-policy/referrer)   
Used to specify information in the [Referer](referer) (sic) header for links away from a page. Use the [`Referrer-Policy`](referrer-policy) header instead.

 [`require-sri-for`](content-security-policy/require-sri-for)   
Requires the use of [SRI](https://developer.mozilla.org/en-US/docs/Glossary/SRI) for scripts or styles on the page.

 [`require-trusted-types-for`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/require-trusted-types-for)   
Enforces [Trusted Types](https://w3c.github.io/webappsec-trusted-types/dist/spec/) at the DOM XSS injection sinks.

<!-- -->

 [`trusted-types`](content-security-policy/trusted-types)   
Used to specify an allow-list of [Trusted Types](https://w3c.github.io/webappsec-trusted-types/dist/spec/) policies. Trusted Types allows applications to lock down DOM XSS injection sinks to only accept non-spoofable, typed values in place of strings.

<!-- -->

[`upgrade-insecure-requests`](content-security-policy/upgrade-insecure-requests)  
Instructs user agents to treat all of a site's insecure URLs (those served over HTTP) as though they have been replaced with secure URLs (those served over HTTPS). This directive is intended for web sites with large numbers of insecure legacy URLs that need to be rewritten.

CSP in workers
--------------

[Workers](https://developer.mozilla.org/en-US/docs/Web/API/Worker) are in general *not* governed by the content security policy of the document (or parent worker) that created them. To specify a content security policy for the worker, set a `Content-Security-Policy` response header for the request which requested the worker script itself.

The exception to this is if the worker script's origin is a globally unique identifier (for example, if its URL has a scheme of data or blob). In this case, the worker does inherit the content security policy of the document or worker that created it.

Multiple content security policies
----------------------------------

The CSP mechanism allows multiple policies being specified for a resource, including via the `Content-Security-Policy` header, the [`Content-Security-Policy-Report-Only`](content-security-policy-report-only) header and a [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) element.

You can use the `Content-Security-Policy` header more than once, as in the example below. Pay special attention to the [`connect-src`](content-security-policy/connect-src) directive here. Even though the second policy would allow the connection, the first policy contains `connect-src 'none'`. Adding additional policies *can only further restrict* the capabilities of the protected resource, which means that there will be no connection allowed and, as the strictest policy, `connect-src 'none'` is enforced.

    Content-Security-Policy: default-src 'self' http://example.com;
                             connect-src 'none';
    Content-Security-Policy: connect-src http://example.com/;
                             script-src http://example.com/

Examples
--------

Example: Disable unsafe inline/eval, only allow loading of resources (images, fonts, scripts, etc.) over https:

    // header
    Content-Security-Policy: default-src https:

    // meta tag
    <meta http-equiv="Content-Security-Policy" content="default-src https:">

Example: Pre-existing site that uses too much inline code to fix but wants to ensure resources are loaded only over HTTPS and to disable plugins:

    Content-Security-Policy: default-src https: 'unsafe-eval' 'unsafe-inline'; object-src 'none'

Example: Do not implement the above policy yet; instead just report violations that would have occurred:

    Content-Security-Policy-Report-Only: default-src https:; report-uri /csp-violation-report-endpoint/

See [Mozilla Web Security Guidelines](https://infosec.mozilla.org/guidelines/web_security#Examples_5) for more examples.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/">Content Security Policy Level 3</a></td><td><span class="spec-WD">Working Draft</span></td><td>Adds <code>manifest-src</code>, <code>navigate-to</code>, <code>report-to</code>, <code>strict-dynamic</code>, <code>worker-src</code>. Undeprecates <code>frame-src</code>. Deprecates <code>report-uri</code> in favor if <code>report-to</code>.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webappsec-mixed-content/">Mixed Content</a></td><td><span class="spec-CR">Candidate Recommendation</span></td><td>Adds <code>block-all-mixed-content</code>.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/webappsec-subresource-integrity/">Subresource Integrity</a></td><td><span class="spec-REC">Recommendation</span></td><td>Adds <code>require-sri-for</code>.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webappsec-upgrade-insecure-requests/">Upgrade Insecure Requests</a></td><td><span class="spec-CR">Candidate Recommendation</span></td><td>Adds <code>upgrade-insecure-requests</code>.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/2/">Content Security Policy Level 2</a></td><td><span class="spec-REC">Recommendation</span></td><td>Adds <code>base-uri</code>, <code>child-src</code>, <code>form-action</code>, <code>frame-ancestors</code>, <code>plugin-types</code>, <code>referrer</code>, and <code>report-uri</code>. Deprecates <code>frame-src</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSP1/">Content Security Policy 1.0</a></td><td><span class="spec-Obsolete">Obsolete</span></td><td>Defines <code>connect-src</code>, <code>default-src</code>, <code>font-src</code>, <code>frame-src</code>, <code>img-src</code>, <code>media-src</code>, <code>object-src</code>, report-uri, <code>sandbox</code>, <code>script-src,</code> and <code>style-src</code>.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Content-Security-Policy`

25

 25  
14   
Uses the non-standard name: `X-Webkit-CSP`

14

23

 23  
4   
Uses the non-standard name: `X-Content-Security-Policy`

10

 10   
Only supporting 'sandbox' directive.

Uses the non-standard name: `X-Content-Security-Policy`

15

7

 7  
6   
Uses the non-standard name: `X-Webkit-CSP`

[`base-uri`](content-security-policy/base-uri)

40

79

35

No

27

10

[`block-all-mixed-content`](content-security-policy/block-all-mixed-content)

Yes

≤79

48

No

Yes

?

[`child-src`](content-security-policy/child-src)

40

15

45

No

27

10

[`connect-src`](content-security-policy/connect-src)

25

14

23

 23   
Prior to Firefox 50, ping attributes of &lt;a&gt; elements weren't covered by connect-src.

No

15

7

[`default-src`](content-security-policy/default-src)

25

14

23

No

15

7

[`font-src`](content-security-policy/font-src)

25

14

23

No

15

7

[`form-action`](content-security-policy/form-action)

40

15

36

No

27

10

[`frame-ancestors`](content-security-policy/frame-ancestors)

40

15

33

 33   
Before Firefox 58, `frame-ancestors` is ignored in `Content-Security-Policy-Report-Only`.

No

26

10

[`frame-src`](content-security-policy/frame-src)

25

14

23

No

15

7

[`img-src`](content-security-policy/img-src)

25

14

23

No

15

7

[`manifest-src`](content-security-policy/manifest-src)

Yes

79

41

No

Yes

No

[`media-src`](content-security-policy/media-src)

25

14

23

No

15

7

`<meta>` element support

Yes

≤18

45

No

Yes

Yes

[`navigate-to`](content-security-policy/navigate-to)

No

No

No

No

No

No

[`object-src`](content-security-policy/object-src)

25

14

23

No

15

7

[`plugin-types`](content-security-policy/plugin-types)

40

15

No

 No   
See [bug 1045899](https://bugzil.la/1045899).

No

27

10

[`prefetch-src`](content-security-policy/prefetch-src)

No

 No   
See [bug 801561](https://crbug.com/801561).

No

 No   
See [bug 801561](https://crbug.com/801561).

No

 No   
See [bug 1457204](https://bugzil.la/1457204).

No

No

No

 No   
See [bug 185070](https://webkit.org/b/185070).

[`referrer`](content-security-policy/referrer)

33 — 56

No

37 — 62

No

? — 43

No

`report-sample`

59

≤79

?

?

46

?

[`report-to`](content-security-policy/report-to)

70

79

No

No

No

No

[`report-uri`](content-security-policy/report-uri)

25

14

23

No

15

7

[`require-sri-for`](content-security-policy/require-sri-for)

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

[`sandbox`](content-security-policy/sandbox)

25

14

50

10

15

7

[`script-src`](content-security-policy/script-src)

25

14

23

No

15

7

[`script-src-attr`](content-security-policy/script-src-attr)

75

79

No

 No   
See [bug 1529337](https://bugzil.la/1529337).

No

62

No

[`script-src-elem`](content-security-policy/script-src-elem)

75

79

No

 No   
See [bug 1529337](https://bugzil.la/1529337).

No

62

No

[`strict-dynamic`](content-security-policy/script-src#strict-dynamic)

52

79

52

No

39

No

[`style-src`](content-security-policy/style-src)

25

14

23

No

15

7

[`style-src-attr`](content-security-policy/style-src-attr)

75

79

No

 No   
See [bug 1529338](https://bugzil.la/1529338).

No

62

No

[`style-src-elem`](content-security-policy/style-src-elem)

75

79

No

 No   
See [bug 1529338](https://bugzil.la/1529338).

No

62

No

[`trusted-types`](content-security-policy/trusted-types)

83

83

73 — 76

Disabled

Disabled From version 73 until version 76 (exclusive): this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

?

No

No

No

No

[`unsafe-hashes`](content-security-policy/script-src#unsafe-hashes)

69

79

No

 No   
See [bug 1343950](https://bugzil.la/1343950).

No

56

No

[`upgrade-insecure-requests`](content-security-policy/upgrade-insecure-requests)

43

17

42

No

30

10.1

Worker support

Yes

≤79

50

No

?

10

[`worker-src`](content-security-policy/worker-src)

59

 59   
Chrome 59 and higher skips the deprecated `child-src` directive.

79

58

No

48

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Content-Security-Policy`

Yes

Yes

23

Yes

7

 7  
5.1   
X-Webkit-CSP

Yes

[`base-uri`](content-security-policy/base-uri)

Yes

Yes

35

?

9.3

Yes

[`block-all-mixed-content`](content-security-policy/block-all-mixed-content)

Yes

Yes

48

?

?

Yes

[`child-src`](content-security-policy/child-src)

Yes

Yes

45

?

9.3

Yes

[`connect-src`](content-security-policy/connect-src)

Yes

Yes

23

?

7

Yes

[`default-src`](content-security-policy/default-src)

Yes

Yes

23

?

7

Yes

[`font-src`](content-security-policy/font-src)

Yes

Yes

23

?

7

Yes

[`form-action`](content-security-policy/form-action)

Yes

Yes

36

?

9.3

Yes

[`frame-ancestors`](content-security-policy/frame-ancestors)

?

Yes

33

 33   
Before Firefox for Android 58, `frame-ancestors` is ignored in `Content-Security-Policy-Report-Only`.

?

9.3

Yes

[`frame-src`](content-security-policy/frame-src)

Yes

Yes

23

?

7

Yes

[`img-src`](content-security-policy/img-src)

Yes

Yes

23

?

7

Yes

[`manifest-src`](content-security-policy/manifest-src)

Yes

Yes

41

?

No

Yes

[`media-src`](content-security-policy/media-src)

Yes

Yes

23

?

7

Yes

`<meta>` element support

Yes

Yes

45

Yes

Yes

Yes

[`navigate-to`](content-security-policy/navigate-to)

No

No

No

No

No

No

[`object-src`](content-security-policy/object-src)

Yes

Yes

23

?

7

Yes

[`plugin-types`](content-security-policy/plugin-types)

Yes

Yes

No

?

9.3

Yes

[`prefetch-src`](content-security-policy/prefetch-src)

No

 No   
See [bug 801561](https://crbug.com/801561).

No

 No   
See [bug 801561](https://crbug.com/801561).

No

 No   
See [bug 1457204](https://bugzil.la/1457204).

No

No

 No   
See [bug 185070](https://webkit.org/b/185070).

No

[`referrer`](content-security-policy/referrer)

4.4.3 — 56

33 — 56

37 — 62

? — 43

No

2.0 — 6.0

`report-sample`

59

59

?

43

?

7.0

[`report-to`](content-security-policy/report-to)

70

70

No

No

No

10.0

[`report-uri`](content-security-policy/report-uri)

Yes

Yes

23

?

7

Yes

[`require-sri-for`](content-security-policy/require-sri-for)

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

[`sandbox`](content-security-policy/sandbox)

Yes

Yes

50

?

7

Yes

[`script-src`](content-security-policy/script-src)

Yes

Yes

23

?

7

Yes

[`script-src-attr`](content-security-policy/script-src-attr)

75

75

No

 No   
See [bug 1529337](https://bugzil.la/1529337).

?

No

No

[`script-src-elem`](content-security-policy/script-src-elem)

75

75

No

 No   
See [bug 1529337](https://bugzil.la/1529337).

?

No

No

[`strict-dynamic`](content-security-policy/script-src#strict-dynamic)

52

52

No

41

No

6.0

[`style-src`](content-security-policy/style-src)

Yes

Yes

23

?

7

Yes

[`style-src-attr`](content-security-policy/style-src-attr)

75

75

No

 No   
See [bug 1529338](https://bugzil.la/1529338).

?

No

No

[`style-src-elem`](content-security-policy/style-src-elem)

75

75

No

 No   
See [bug 1529338](https://bugzil.la/1529338).

?

No

No

[`trusted-types`](content-security-policy/trusted-types)

83

83

83

73 — 76

Disabled

Disabled From version 73 until version 76 (exclusive): this feature is behind the `#enable-experimental-productivity-features` preference (needs to be set to `Enabled`). To change preferences in Chrome, visit chrome://flags.

No

No

No

No

[`unsafe-hashes`](content-security-policy/script-src#unsafe-hashes)

69

69

No

48

No

No

[`upgrade-insecure-requests`](content-security-policy/upgrade-insecure-requests)

43

43

42

30

10.3

4.0

Worker support

Yes

Yes

50

?

10

Yes

[`worker-src`](content-security-policy/worker-src)

59

 59   
Chrome 59 and higher skips the deprecated `child-src` directive.

59

 59   
Chrome 59 and higher skips the deprecated `child-src` directive.

58

45

No

7.0

See also
--------

-   [`Content-Security-Policy-Report-Only`](content-security-policy-report-only)
-   [Learn about: Content Security Policy](../csp)
-   [Content Security in WebExtensions](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Content_Security_Policy)
-   [Adopting a strict policy](https://csp.withgoogle.com/docs/strict-csp.html)
-   [CSP Evaluator](https://github.com/google/csp-evaluator) - Evaluate your Content Security Policy

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy</a>
