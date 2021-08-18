Content-Security-Policy-Report-Only
===================================

The HTTP `Content-Security-Policy-Report-Only` response header allows web developers to experiment with policies by monitoring (but not enforcing) their effects. These violation reports consist of [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON) documents sent via an HTTP `POST` request to the specified URI.

For more information, see also this article on [Content Security Policy (CSP)](../csp).

Header type

[Response header](https://developer.mozilla.org/en-US/docs/Glossary/Response_header)

[Forbidden header name](https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name)

no

This header is not supported inside a [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) element.

Syntax
------

    Content-Security-Policy-Report-Only: <policy-directive>; <policy-directive>

Directives
----------

The directives of the [`Content-Security-Policy`](content-security-policy) header can also be applied to `Content-Security-Policy-Report-Only`.

The CSP [`report-uri`](content-security-policy/report-uri) directive should be used with this header, otherwise this header will be an expensive no-op machine.

Examples
--------

This header reports violations that would have occurred. You can use this to iteratively work on your content security policy. You observe how your site behaves, watching for violation reports, or [malware redirects](https://secure.wphackedhelp.com/blog/wordpress-malware-redirect-hack-cleanup/), then choose the desired policy enforced by the [`Content-Security-Policy`](content-security-policy) header.

    Content-Security-Policy-Report-Only: default-src https:; report-uri /csp-violation-report-endpoint/

If you still want to receive reporting, but also want to enforce a policy, use the [`Content-Security-Policy`](content-security-policy) header with the [`report-uri`](content-security-policy/report-uri) directive.

    Content-Security-Policy: default-src https:; report-uri /csp-violation-report-endpoint/

Violation report syntax
-----------------------

The report JSON object contains the following data:

`blocked-uri`  
The URI of the resource that was blocked from loading by the Content Security Policy. If the blocked URI is from a different origin than the document-uri, then the blocked URI is truncated to contain just the scheme, host, and port.

`disposition`  
Either `"enforce"` or `"report"` depending on whether the [`Content-Security-Policy`](content-security-policy) header or the `Content-Security-Policy-Report-Only` header is used.

`document-uri`  
The URI of the document in which the violation occurred.

`effective-directive`  
The directive whose enforcement caused the violation.

`original-policy`  
The original policy as specified by the `Content-Security-Policy-Report-Only` HTTP header.

`referrer`  
The referrer of the document in which the violation occurred.

`script-sample`  
The first 40 characters of the inline script, event handler, or style that caused the violation.

`status-code`  
The HTTP status code of the resource on which the global object was instantiated.

`violated-directive`  
The name of the policy section that was violated.

Sample violation report
-----------------------

Let's consider a page located at `http://example.com/signup.html`. It uses the following policy, disallowing everything but stylesheets from `cdn.example.com`.

    Content-Security-Policy-Report-Only: default-src 'none'; style-src cdn.example.com; report-uri /_/csp-reports

The HTML of `signup.html` looks like this:

    <!DOCTYPE html>
    <html>
      <head>
        <title>Sign Up</title>
        <link rel="stylesheet" href="css/style.css">
      </head>
      <body>
        ... Content ...
      </body>
    </html>

Can you spot the violation? Stylesheets are only allowed to be loaded from `cdn.example.com`, yet the website tries to load one from its own origin (`http://example.com`). A browser capable of enforcing CSP will send the following violation report as a POST request to `http://example.com/_/csp-reports`, when the document is visited:

    {
      "csp-report": {
        "document-uri": "http://example.com/signup.html",
        "referrer": "",
        "blocked-uri": "http://example.com/css/style.css",
        "violated-directive": "style-src cdn.example.com",
        "original-policy": "default-src 'none'; style-src cdn.example.com; report-uri /_/csp-reports",
        "disposition": "report"
      }
    }

As you can see, the report includes the full path to the violating resource in `blocked-uri`. This is not always the case. For example, when the `signup.html` would attempt to load CSS from `http://anothercdn.example.com/stylesheet.css`, the browser would *not* include the full path but only the origin (`http://anothercdn.example.com`). This is done to prevent leaking sensitive information about cross-origin resources.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-csp/">Content Security Policy Level 3</a></td><td><span class="spec-WD">Working Draft</span></td><td>No changes.</td></tr><tr class="even"><td><a href="https://w3c.github.io/webappsec-csp/2/">Content Security Policy Level 2</a></td><td><span class="spec-REC">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Content-Security-Policy-Report-Only`

25

14

23

10

15

7

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Content-Security-Policy-Report-Only`

4.4

Yes

23

?

7

Yes

See also
--------

-   [`Content-Security-Policy`](content-security-policy)
-   CSP [`report-uri`](content-security-policy/report-uri) directive
-   [Content Security in WebExtensions](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Content_Security_Policy)
-   [Display security and privacy policies In Firefox Developer Tools](https://developer.mozilla.org/en-US/docs/Tools/GCLI/Display_security_and_privacy_policies)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy-Report-Only$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy-Report-Only" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy-Report-Only</a>
