Upgrade-Insecure-Requests
=========================

The HTTP `Upgrade-Insecure-Requests` request header sends a signal to the server expressing the client’s preference for an encrypted and authenticated response, and that it can successfully handle the [`upgrade-insecure-requests`](content-security-policy/upgrade-insecure-requests) [CSP](https://developer.mozilla.org/en-US/docs/Web/Security/CSP) directive.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Upgrade-Insecure-Requests: 1

Examples
--------

A client's request signals to the server that it supports the upgrade mechanisms of [`upgrade-insecure-requests`](content-security-policy/upgrade-insecure-requests):

    GET / HTTP/1.1 
    Host: example.com 
    Upgrade-Insecure-Requests: 1

The server can now redirect to a secure version of the site. A [`Vary`](vary) header can be used so that the site isn't served by caches to clients that don’t support the upgrade mechanism.

    Location: https://example.com/ 
    Vary: Upgrade-Insecure-Requests

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-upgrade-insecure-requests/#preference">Upgrade Insecure Requests<br />
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

`Upgrade-Insecure-Requests`

44

17

48

No

31

10.1

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Upgrade-Insecure-Requests`

44

44

48

32

10.3

4.0

See also
--------

-   [`Content-Security-Policy`](content-security-policy)
-   CSP [`upgrade-insecure-requests`](content-security-policy/upgrade-insecure-requests) directive

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests</a>
