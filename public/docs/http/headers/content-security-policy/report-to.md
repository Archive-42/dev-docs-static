CSP: report-to
==============

The `Content-Security-Policy` **`Report-To`** HTTP response header field instructs the user agent to store reporting endpoints for an origin.

    Content-Security-Policy: ...; report-to groupname

The directive has no effect in and of itself, but only gains meaning in combination with other directives.

CSP version

1

Directive type

[Reporting directive](https://developer.mozilla.org/en-US/docs/Glossary/Reporting_directive)

This directive is not supported in the [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) element.

Syntax
------

    Content-Security-Policy: report-to <json-field-value>;

Examples
--------

See [`Content-Security-Policy-Report-Only`](../content-security-policy-report-only) for more information and examples.

    Report-To: { "group": "csp-endpoint",
                 "max_age": 10886400,
                 "endpoints": [
                   { "url": "https://example.com/csp-reports" }
                 ] },
               { "group": "hpkp-endpoint",
                 "max_age": 10886400,
                 "endpoints": [
                   { "url": "https://example.com/hpkp-reports" }
                 ] }
    Content-Security-Policy: ...; report-to csp-endpoint

    Report-To: { "group": "endpoint-1",
                 "max_age": 10886400,
                 "endpoints": [
                   { "url": "https://example.com/reports" },
                   { "url": "https://backup.com/reports" }
                 ] } 

    Content-Security-Policy: ...; report-to endpoint-1

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`report-to`

70

79

No

No

No

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`report-to`

70

70

No

No

No

10.0

See also
--------

-   [`Content-Security-Policy`](../content-security-policy)
-   [`Content-Security-Policy-Report-Only`](../content-security-policy-report-only)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/report-to$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/report-to" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/report-to</a>
