Strict-Transport-Security
=========================

The `Strict-Transport-Security` response header (often abbreviated as [HSTS](https://developer.mozilla.org/en-US/docs/Glossary/HSTS)) lets a web site tell browsers that it should only be accessed using HTTPS, instead of using HTTP.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Strict-Transport-Security: max-age=<expire-time>
    Strict-Transport-Security: max-age=<expire-time>; includeSubDomains
    Strict-Transport-Security: max-age=<expire-time>; preload

Directives
----------

`max-age=<expire-time>`  
The time, in seconds, that the browser should remember that a site is only to be accessed using HTTPS.

 `includeSubDomains` <span class="inlineIndicator optional optionalInline">Optional</span>   
If this optional parameter is specified, this rule applies to all of the site's subdomains as well.

 `preload` <span class="inlineIndicator optional optionalInline">Optional</span>   
See [Preloading Strict Transport Security](#Preloading_Strict_Transport_Security) for details. Not part of the specification.

Description
-----------

If a website accepts a connection through HTTP and redirects to HTTPS, visitors may initially communicate with the non-encrypted version of the site before being redirected, if, for example, the visitor types http://www.foo.com/ or even just foo.com. This creates an opportunity for a man-in-the-middle attack. The redirect could be exploited to direct visitors to a malicious site instead of the secure version of the original site.

The HTTP Strict Transport Security header informs the browser that it should never load a site using HTTP and should automatically convert all attempts to access the site using HTTP to HTTPS requests instead.

**Note:** The `Strict-Transport-Security` header is **ignored** by the browser when your site is accessed using HTTP; this is because an attacker may intercept HTTP connections and inject the header or remove it. When your site is accessed over HTTPS with no certificate errors, the browser knows your site is HTTPS capable and will honor the `Strict-Transport-Security` header.

### An example scenario

You log into a free WiFi access point at an airport and start surfing the web, visiting your online banking service to check your balance and pay a couple of bills. Unfortunately, the access point you're using is actually a hacker's laptop, and they're intercepting your original HTTP request and redirecting you to a clone of your bank's site instead of the real thing. Now your private data is exposed to the hacker.

Strict Transport Security resolves this problem; as long as you've accessed your bank's web site once using HTTPS, and the bank's web site uses Strict Transport Security, your browser will know to automatically use only HTTPS, which prevents hackers from performing this sort of man-in-the-middle attack.

### How the browser handles it

The first time your site is accessed using HTTPS and it returns the `Strict-Transport-Security` header, the browser records this information, so that future attempts to load the site using HTTP will automatically use HTTPS instead.

When the expiration time specified by the Strict-Transport-Security header elapses, the next attempt to load the site via HTTP will proceed as normal instead of automatically using HTTPS.

Whenever the Strict-Transport-Security header is delivered to the browser, it will update the expiration time for that site, so sites can refresh this information and prevent the timeout from expiring. Should it be necessary to disable Strict Transport Security, setting the max-age to 0 (over a https connection) will immediately expire the `Strict-Transport-Security` header, allowing access via http.

Preloading Strict Transport Security
------------------------------------

Google maintains [an HSTS preload service](https://hstspreload.org/). By following the guidelines and successfully submitting your domain, browsers will never connect to your domain using an insecure connection. While the service is hosted by Google, all browsers have stated an intent to use (or actually started using) the preload list. However, it is not part of the HSTS specification and should not be treated as official.

-   Information regarding the HSTS preload list in Chrome : <https://www.chromium.org/hsts>
-   Consultation of the Firefox HSTS preload list : [nsSTSPreloadList.inc](https://hg.mozilla.org/mozilla-central/raw-file/tip/security/manager/ssl/nsSTSPreloadList.inc)

Examples
--------

All present and future subdomains will be HTTPS for a max-age of 1 year. This blocks access to pages or sub domains that can only be served over HTTP.

    Strict-Transport-Security: max-age=31536000; includeSubDomains

In the following example, `max-age` is set to 2 years, raised from what was a former limit `max-age` of 1 year. Note that 1 year is acceptable for a domain to be included in browsers' HSTS preload lists. 2 years is, however, the recommended goal as a website's final HSTS configuration as explained on <https://hstspreload.org>. It also suffixed with `preload` which is necessary for inclusion in most major web browsers' HSTS preload lists, e.g. Chromium, Edge, & Firefox.

    Strict-Transport-Security: max-age=63072000; includeSubDomains; preload

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc6797">HTTP Strict Transport Security (HSTS)</a></td><td><span class="spec-RFC">IETF RFC</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Strict-Transport-Security`

4

12

4

11

12

7

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Strict-Transport-Security`

4.4

18

Yes

?

7

Yes

See also
--------

-   Blog post: [HTTP Strict Transport Security has landed!](https://blog.sidstamm.com/2010/08/http-strict-transport-security-has.html)
-   Blog post: [HTTP Strict Transport Security (force HTTPS)](https://hacks.mozilla.org/2010/08/firefox-4-http-strict-transport-security-force-https/)
-   OWASP Article: [HTTP Strict Transport Security](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html)
-   Wikipedia: [HTTP Strict Transport Security](https://en.wikipedia.org/wiki/HTTP%20Strict%20Transport%20Security)
-   Browser test site: [HSTS and HPKP test](https://projects.dm.id.lv/Public-Key-Pins_test)
-   [Features restricted to secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts/features_restricted_to_secure_contexts)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security</a>
