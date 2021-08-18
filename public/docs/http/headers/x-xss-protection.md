X-XSS-Protection
================

The HTTP `X-XSS-Protection` response header is a feature of Internet Explorer, Chrome and Safari that stops pages from loading when they detect reflected cross-site scripting ([XSS](https://developer.mozilla.org/en-US/docs/Glossary/XSS)) attacks. Although these protections are largely unnecessary in modern browsers when sites implement a strong [`Content-Security-Policy`](content-security-policy) that disables the use of inline JavaScript (`'unsafe-inline'`), they can still provide protections for users of older web browsers that don't yet support [CSP](https://developer.mozilla.org/en-US/docs/Glossary/CSP).

-   Chrome has [removed their XSS Auditor](https://www.chromestatus.com/feature/5021976655560704)
-   Firefox has not, and [will not implement `X-XSS-Protection`](https://bugzilla.mozilla.org/show_bug.cgi?id=528661)
-   Edge has [retired their XSS filter](https://blogs.windows.com/windowsexperience/2018/07/25/announcing-windows-10-insider-preview-build-17723-and-build-18204/)

This means that if you do not need to support legacy browsers, it is recommended that you use `Content-Security-Policy` without allowing `unsafe-inline` scripts instead.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    X-XSS-Protection: 0
    X-XSS-Protection: 1
    X-XSS-Protection: 1; mode=block
    X-XSS-Protection: 1; report=<reporting-uri>

0  
Disables XSS filtering.

1  
Enables XSS filtering (usually default in browsers). If a cross-site scripting attack is detected, the browser will sanitize the page (remove the unsafe parts).

1; mode=block  
Enables XSS filtering. Rather than sanitizing the page, the browser will prevent rendering of the page if an attack is detected.

1; report=&lt;reporting-URI&gt; (Chromium only)  
Enables XSS filtering. If a cross-site scripting attack is detected, the browser will sanitize the page and report the violation. This uses the functionality of the CSP [`report-uri`](content-security-policy/report-uri) directive to send a report.

Example
-------

Block pages from loading when they detect reflected XSS attacks:

    X-XSS-Protection: 1; mode=block

PHP

    header("X-XSS-Protection: 1; mode=block");

Apache (.htaccess)

    <IfModule mod_headers.c> 
      Header set X-XSS-Protection "1; mode=block" 
    </IfModule>

Nginx

    add_header "X-XSS-Protection" "1; mode=block";

Specifications
--------------

Not part of any specifications or drafts.

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`X-XSS-Protection`

4 — 78

12 — 17

No

8

? — 65

Yes

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`X-XSS-Protection`

No

? — 78

No

? — 56

Yes

Yes

See also
--------

-   [`Content-Security-Policy`](content-security-policy)
-   [Controlling the XSS Filter – Microsoft](https://blogs.msdn.microsoft.com/ieinternals/2011/01/31/controlling-the-xss-filter/)
-   [Understanding XSS Auditor – Virtue Security](https://www.virtuesecurity.com/blog/understanding-xss-auditor/)
-   [The misunderstood X-XSS-Protection – blog.innerht.ml](https://blog.innerht.ml/the-misunderstood-x-xss-protection/)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-XSS-Protection$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-XSS-Protection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-XSS-Protection</a>
