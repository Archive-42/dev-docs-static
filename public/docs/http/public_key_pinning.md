Public Key Pinning
==================

**Deprecated**  
This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#Browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note:** Public Key Pinning mechanism was deprecated in favor of [Certificate Transparency](https://developer.mozilla.org/en-US/docs/Web/Security/Certificate_Transparency) and [`Expect-CT`](headers/expect-ct) header.

**HTTP Public Key Pinning** ([HPKP](https://developer.mozilla.org/en-US/docs/Glossary/HPKP)) was a security feature that used to tell a web client to associate a specific cryptographic public key with a certain web server to decrease the risk of [MITM](https://developer.mozilla.org/en-US/docs/Glossary/MITM) attacks with forged certificates. It has been removed in modern browsers and is no longer supported.

To ensure the authenticity of a server's public key used in [TLS](https://developer.mozilla.org/en-US/docs/Glossary/TLS) sessions, this public key is wrapped into a X.509 certificate which is usually signed by a certificate authority ([CA](https://developer.mozilla.org/en-US/docs/Glossary/CA)). Web clients such as browsers trust a lot of these CAs, which can all create certificates for arbitrary domain names. If an attacker is able to compromise a single CA, they can perform MITM attacks on various TLS connections. HPKP can circumvent this threat for the [HTTPS](https://developer.mozilla.org/en-US/docs/Glossary/HTTPS) protocol by telling the client which public key belongs to a certain web server.

HPKP is a *Trust on First Use* ([TOFU](https://developer.mozilla.org/en-US/docs/Glossary/TOFU)) technique. The first time a web server tells a client via a special HTTP header which public keys belong to it, the client stores this information for a given period of time. When the client visits the server again, it expects at least one certificate in the certificate chain to contain a public key whose fingerprint is already known via HPKP. If the server delivers an unknown public key, the client should present a warning to the user.

Firefox and Chrome **disable pin validation** for pinned hosts whose validated certificate chain terminates at a **user-defined trust anchor** (rather than a built-in trust anchor). This means that for users who imported custom root certificates all pinning violations are ignored.

Enabling HPKP
-------------

To enable this feature for your site, you need to return the [`Public-Key-Pins`](headers/public-key-pins) HTTP header when your site is accessed over HTTPS:

    Public-Key-Pins: pin-sha256="base64=="; max-age=expireTime [; includeSubDomains][; report-uri="reportURI"]

`pin-sha256`  
The quoted string is the Base64 encoded *Subject Public Key Information* ([SPKI](https://developer.mozilla.org/en-US/docs/Glossary/SPKI)) fingerprint. It is possible to specify multiple pins for different public keys. Some browsers might allow other hashing algorithms than SHA-256 in the future. See below on how to extract this information out of a certificate or key file.

`max-age`  
The time, in seconds, that the browser should remember that this site is only to be accessed using one of the defined keys.

 `includeSubDomains` <span class="inlineIndicator optional optionalInline">Optional</span>   
If this optional parameter is specified, this rule applies to all of the site's subdomains as well.

 `report-uri` <span class="inlineIndicator optional optionalInline">Optional</span>   
If this optional parameter is specified, pin validation failures are reported to the given URL.

**Note**: The current specification requires including a second pin for a backup key which isn't yet used in production. This allows for changing the server's public key without breaking accessibility for clients that have already noted the pins. This is important for example when the former key gets compromised.

### Extracting the Base64 encoded public key information

**Note:** While the example below shows how to set a pin on a server certificate, it is recommended to place the pin on the intermediate certificate of the CA that issued the server certificate, to ease certificates renewals and rotations.

First you need to extract the public key information from your certificate or key file and encode them using Base64.

The following commands will help you extract the Base64 encoded information from a key file, a certificate signing request, or a certificate.

    openssl rsa -in my-rsa-key-file.key -outform der -pubout | openssl dgst -sha256 -binary | openssl enc -base64

    openssl ec -in my-ecc-key-file.key -outform der -pubout | openssl dgst -sha256 -binary | openssl enc -base64

    openssl req -in my-signing-request.csr -pubkey -noout | openssl pkey -pubin -outform der | openssl dgst -sha256 -binary | openssl enc -base64

    openssl x509 -in my-certificate.crt -pubkey -noout | openssl pkey -pubin -outform der | openssl dgst -sha256 -binary | openssl enc -base64

The following command will extract the Base64 encoded information for a website.

    openssl s_client -servername www.example.com -connect www.example.com:443 | openssl x509 -pubkey -noout | openssl pkey -pubin -outform der | openssl dgst -sha256 -binary | openssl enc -base64

### Example HPKP Header

    Public-Key-Pins: 
      pin-sha256="cUPcTAZWKaASuYWhhneDttWpY3oBAkE3h2+soZS7sWs="; 
      pin-sha256="M8HztCzM3elUxkcjR2S5P4hhyBNf6lHkmjAHKhpGPWE="; 
      max-age=5184000; includeSubDomains; 
      report-uri="https://www.example.org/hpkp-report"

In this example, **pin-sha256="cUPcTAZWKaASuYWhhneDttWpY3oBAkE3h2+soZS7sWs="** pins the server's public key used in production. The second pin declaration **pin-sha256="M8HztCzM3elUxkcjR2S5P4hhyBNf6lHkmjAHKhpGPWE="** also pins the backup key. **max-age=5184000** tells the client to store this information for two months, which is a reasonable time limit according to the IETF RFC. This key pinning is also valid for all subdomains, which is told by the **includeSubDomains** declaration. Finally, **report-uri="https://www.example.net/hpkp-report"** explains where to report pin validation failures.

### Report-Only header

Instead of using a [`Public-Key-Pins`](headers/public-key-pins) header you can also use a [`Public-Key-Pins-Report-Only`](headers/public-key-pins-report-only) header. This header only sends reports to the `report-uri` specified in the header and does still allow browsers to connect to the webserver even if the pinning is violated.

### Setting up your webserver to include the HPKP header

The concrete steps necessary to deliver the HPKP header depend on the web server you use.

**Note:** These examples use a max-age of two months and include all subdomains. It is advised to verify that this setup will work for your server.

HPKP has the potential to lock out users for a long time if used incorrectly! The use of backup certificates and/or pinning the CA certificate is recommended.

#### Apache

Adding a line similar to the following to your webserver's config will enable HPKP on your Apache. This requires `mod_headers` enabled.

    Header always set Public-Key-Pins "pin-sha256=\"base64+primary==\"; pin-sha256=\"base64+backup==\"; max-age=5184000; includeSubDomains"

#### Nginx

Adding the following line and inserting the appropriate `pin-sha256="..."` values will enable HPKP on your nginx. This requires the `ngx_http_headers_module.`

    add_header Public-Key-Pins 'pin-sha256="base64+primary=="; pin-sha256="base64+backup=="; max-age=5184000; includeSubDomains' always;

#### Lighttpd

The following line with your relevant key information (pin-sha256="..." fields) will enable HPKP on lighttpd.

    setenv.add-response-header  = ( "Public-Key-Pins" => "pin-sha256=\"base64+primary==\"; pin-sha256=\"base64+backup==\"; max-age=5184000; includeSubDomains")

**Note:** This requires the `mod_setenv` server.module loaded which can be included by the following if not already loaded.

    server.modules += ( "mod_setenv" )

#### IIS

Add the following line to the Web.config file to send the `Public-Key-Pins` header:

    <system.webServer>
      ...

      <httpProtocol>
        <customHeaders>
          <add name="Public-Key-Pins" value="pin-sha256=&quot;base64+primary==&quot;; pin-sha256=&quot;base64+backup==&quot;; max-age=5184000; includeSubDomains" />
        </customHeaders>
      </httpProtocol>

      ...
    </system.webServer>

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

[`Public-Key-Pins`](headers/public-key-pins)

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

[`Public-Key-Pins`](headers/public-key-pins)

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

-   [`Public-Key-Pins`](headers/public-key-pins)
-   [`Public-Key-Pins-Report-Only`](headers/public-key-pins-report-only)
-   Browser test site: [HSTS and HPKP test](https://projects.dm.id.lv/Public-Key-Pins_test)
-   [`Expect-CT`](headers/expect-ct)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Public_Key_Pinning$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Public_Key_Pinning" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Public_Key_Pinning</a>
