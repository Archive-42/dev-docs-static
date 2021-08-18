Expect-CT
=========

The `Expect-CT` header lets sites opt in to reporting and/or enforcement of [Certificate Transparency](https://developer.mozilla.org/en-US/docs/Web/Security/Certificate_Transparency) requirements, to prevent the use of misissued certificates for that site from going unnoticed.

CT requirements can be satisfied via any one of the following mechanisms:

-   X.509v3 certificate extension to allow embedding of signed certificate timestamps issued by individual logs
-   A TLS extension of type `signed_certificate_timestamp` sent during the handshake
-   Supporting OCSP stapling (that is, the `status_request` TLS extension) and providing a `SignedCertificateTimestampList`

When a site enables the `Expect-CT` header, they are requesting that the browser check that any certificate for that site appears in **[public CT logs](https://www.certificate-transparency.org/known-logs)**.

Browsers **ignore** the `Expect-CT` header over HTTP; the header only has effect on HTTPS connections.

The `Expect-CT` will likely become obsolete in June 2021. Since May 2018 new certificates are expected to support SCTs by default. Certificates before March 2018 were allowed to have a lifetime of 39 months, those will all be expired in June 2021.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Expect-CT: report-uri="<uri>",
               enforce,
               max-age=<age>

Directives
----------

`max-age`  
The number of seconds after reception of the `Expect-CT` header field during which the user agent should regard the host of the received message as a known `Expect-CT` host.

If a cache receives a value greater than it can represent, or if any of its subsequent calculations overflows, the cache will consider this value to be either 2,147,483,648 (2<sup>31</sup>) or the greatest positive integer it can represent.

 `report-uri="<uri>"` <span class="inlineIndicator optional optionalInline">Optional</span>   
The URI where the user agent should report `Expect-CT` failures.

When present with the `enforce` directive, the configuration is referred to as an "enforce-and-report" configuration, signalling to the user agent both that compliance to the Certificate Transparency policy should be enforced *and* that violations should be reported.

 `enforce` <span class="inlineIndicator optional optionalInline">Optional</span>   
Signals to the user agent that compliance with the Certificate Transparency policy should be enforced (rather than only reporting compliance) and that the user agent should refuse future connections that violate its Certificate Transparency policy.

When both the `enforce` directive and the `report-uri` directive are present, the configuration is referred to as an "enforce-and-report" configuration, signalling to the user agent both that compliance to the Certificate Transparency policy should be enforced and that violations should be reported.

Example
-------

The following example specifies enforcement of Certificate Transparency for 24 hours and reports violations to `foo.example`.

    Expect-CT: max-age=86400, enforce, report-uri="https://foo.example/report"

Notes
-----

Root CAs manually added to the trust store override and suppress `Expect-CT` reports/enforcement.

Browsers will not remember an `Expect-CT` policy, unless the site has 'proven' it can serve a certificate satisfying the certificate transparency requirements. Browsers implement their own trust model regarding which CT logs are considered trusted for the certificate to have been logged to.

Builds of Chrome are designed to stop enforcing the `Expect-CT` policy 10 weeks after the installation's build date.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/draft-ietf-httpbis-expect-ct-08">Internet Draft</a></td><td>Expect-CT Extension for HTTP</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Expect-CT`

61

 61   
Before later builds of Chrome 64, invalid Expect-CT reports would be sent. Newer versions do not send reports after 10 weeks from the build date. See [bug 786563](https://crbug.com/786563).

≤79

?

?

48

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Expect-CT`

No

61

?

45

?

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Expect-CT$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Expect-CT" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Expect-CT</a>
