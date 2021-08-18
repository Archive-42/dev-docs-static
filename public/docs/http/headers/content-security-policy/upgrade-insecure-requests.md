CSP: upgrade-insecure-requests
==============================

The HTTP [`Content-Security-Policy`](../content-security-policy) (CSP) `upgrade-insecure-requests` directive instructs user agents to treat all of a site's insecure URLs (those served over HTTP) as though they have been replaced with secure URLs (those served over HTTPS). This directive is intended for web sites with large numbers of insecure legacy URLs that need to be rewritten.

The `upgrade-insecure-requests` directive is evaluated before [`block-all-mixed-content`](block-all-mixed-content) and if it is set, the latter is effectively a no-op. It is recommended to set either directive, but not both, unless you want to force HTTPS on older browsers that do not force it after a redirect to HTTP.

The `upgrade-insecure-requests` directive will not ensure that users visiting your site via links on third-party sites will be upgraded to HTTPS for the top-level navigation and thus does not replace the [`Strict-Transport-Security`](../strict-transport-security) ([HSTS](https://developer.mozilla.org/en-US/docs/Glossary/HSTS)) header, which should still be set with an appropriate `max-age` to ensure that users are not subject to SSL stripping attacks.

Syntax
------

    Content-Security-Policy: upgrade-insecure-requests;

Examples
--------

    // header
    Content-Security-Policy: upgrade-insecure-requests;

    // meta tag
    <meta http-equiv="Content-Security-Policy" content="upgrade-insecure-requests">

With the above header set on a domain example.com that wants to migrate from HTTP to HTTPS, non-navigational insecure resource requests are automatically upgraded (first-party as well as third-party requests).

    <img src="http://example.com/image.png">
    <img src="http://not-example.com/image.png">

These URLs will be rewritten before the request is made, meaning that no insecure requests will hit the network. Note that, if the requested resource is not actually available via HTTPS, the request will fail without any fallback to HTTP.

    <img src="https://example.com/image.png">
    <img src="https://not-example.com/image.png">

Navigational upgrades to third-party resources brings a significantly higher potential for breakage, these are not upgraded:

    <a href="https://example.com/">Home</a>
    <a href="http://not-example.com/">Home</a>

### Finding insecure requests

With the help of the [`Content-Security-Policy-Report-Only`](../content-security-policy-report-only) header and the [`report-uri`](report-uri) directive, you can set-up an enforced policy and a reported policy like this:

    Content-Security-Policy: upgrade-insecure-requests; default-src https: 
    Content-Security-Policy-Report-Only: default-src https:; report-uri /endpoint

That way, you still upgrade insecure requests on your secure site, but the only monitoring policy is violated and reports insecure resources to your endpoint.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-upgrade-insecure-requests/#delivery">Upgrade Insecure Requests<br />
<span class="small">The definition of 'upgrade-insecure-requests' in that specification.</span></a></td><td><span class="spec-CR">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`upgrade-insecure-requests`

43

17

42

No

30

10.1

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`upgrade-insecure-requests`

43

43

42

30

10.3

4.0

See also
--------

-   [`Content-Security-Policy`](../content-security-policy)
-   [`Upgrade-Insecure-Requests`](../upgrade-insecure-requests) header
-   [`Strict-Transport-Security`](../strict-transport-security) ([HSTS](https://developer.mozilla.org/en-US/docs/Glossary/HSTS)) header
-   [`block-all-mixed-content`](block-all-mixed-content)
-   [Mixed content](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/upgrade-insecure-requests$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/upgrade-insecure-requests" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/upgrade-insecure-requests</a>
