Public-Key-Pins
===============

**Deprecated**  
This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#Browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note:** Public Key Pinning mechanism was deprecated in favor of [Certificate Transparency](https://developer.mozilla.org/en-US/docs/Web/Security/Certificate_Transparency) and [`Expect-CT`](expect-ct) header.

The HTTP `Public-Key-Pins` response header used to associate a specific cryptographic public [key](https://developer.mozilla.org/en-US/docs/Glossary/key) with a certain web server to decrease the risk of [MITM](https://developer.mozilla.org/en-US/docs/Glossary/MITM) attacks with forged certificates, however, it has been removed from modern browsers and is no longer supported. Use [Certificate Transparency](https://developer.mozilla.org/en-US/docs/Web/Security/Certificate_Transparency) and [`Expect-CT`](expect-ct) header instead.

For more information, see the [HTTP Public Key Pinning](../public_key_pinning) article.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Public-Key-Pins: pin-sha256="<pin-value>"; 
                     max-age=<expire-time>; 
                     includeSubDomains; 
                     report-uri="<uri>"

Directives
----------

`pin-sha256="<pin-value>"`  
The quoted string is the Base64 encoded Subject Public Key Information ([SPKI](https://developer.mozilla.org/en-US/docs/Glossary/SPKI)) fingerprint. It is possible to specify multiple pins for different public keys. Some browsers might allow other hashing algorithms than SHA-256 in the future.

`max-age=<expire-time>`  
The time, in seconds, that the browser should remember that this site is only to be accessed using one of the defined keys.

 `includeSubDomains `<span class="inlineIndicator optional optionalInline">Optional</span>   
If this optional parameter is specified, this rule applies to all of the site's subdomains as well.

 `report-uri="<uri>"` <span class="inlineIndicator optional optionalInline">Optional</span>   
If this optional parameter is specified, pin validation failures are reported to the given URL.

Example
-------

HPKP has the potential to lock out users for a long time if used incorrectly! The use of backup certificates and/or pinning the CA certificate is recommended.

    Public-Key-Pins: 
      pin-sha256="cUPcTAZWKaASuYWhhneDttWpY3oBAkE3h2+soZS7sWs="; 
      pin-sha256="M8HztCzM3elUxkcjR2S5P4hhyBNf6lHkmjAHKhpGPWE="; 
      max-age=5184000; includeSubDomains; 
      report-uri="https://www.example.org/hpkp-report"

In this example, **pin-sha256="cUPcTAZWKaASuYWhhneDttWpY3oBAkE3h2+soZS7sWs="** pins the server's public key used in production. The second pin declaration **pin-sha256="M8HztCzM3elUxkcjR2S5P4hhyBNf6lHkmjAHKhpGPWE="** also pins the backup key. **max-age=5184000** tells the client to store this information for two months, which is a reasonable time limit according to the IETF RFC. This key pinning is also valid for all subdomains, which is told by the **includeSubDomains** declaration. Finally, **report-uri="https://www.example.org/hpkp-report"** explains where to report pin validation failures.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7469#section-2.1">RFC 7469, section 2.1: Public-Key-Pins</a></td><td>Public Key Pinning Extension for HTTP</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Public-Key-Pins`

? — 72

No

35 — 72

35 — 72

72

Disabled

Disabled From version 72: this feature is behind the `security.cert_pinning.hpkp.enabled` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

? — 60

No

report-uri

46 — 72

No

No

 No   
See [bug 1091176](https://bugzil.la/1091176).

No

33 — 60

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Public-Key-Pins`

No

? — 72

35

? — 51

No

? — 11.0

report-uri

No

? — 72

No

33 — 51

No

? — 11.0

See also
--------

-   [`Public-Key-Pins-Report-Only`](public-key-pins-report-only)
-   [`Expect-CT`](expect-ct)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Public-Key-Pins$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Public-Key-Pins" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Public-Key-Pins</a>
