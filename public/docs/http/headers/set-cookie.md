Set-Cookie
==========

The `Set-Cookie` HTTP response header is used to send a cookie from the server to the user agent, so the user agent can send it back to the server later. To send multiple cookies, multiple `Set-Cookie` headers should be sent in the same response.

Browsers block frontend JavaScript code from accessing the `Set Cookie` header, as required by the Fetch spec, which defines `Set-Cookie` as a [forbidden response-header name](https://fetch.spec.whatwg.org/#forbidden-response-header-name) that [must be filtered out](https://fetch.spec.whatwg.org/#ref-for-forbidden-response-header-name%E2%91%A0) from any response exposed to frontend code.

For more information, see the [guide on HTTP cookies](../cookies).

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr><tr class="odd"><td><a href="https://fetch.spec.whatwg.org/#forbidden-response-header-name">Forbidden response-header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Set-Cookie: <cookie-name>=<cookie-value> 
    Set-Cookie: <cookie-name>=<cookie-value>; Expires=<date>
    Set-Cookie: <cookie-name>=<cookie-value>; Max-Age=<non-zero-digit>
    Set-Cookie: <cookie-name>=<cookie-value>; Domain=<domain-value>
    Set-Cookie: <cookie-name>=<cookie-value>; Path=<path-value>
    Set-Cookie: <cookie-name>=<cookie-value>; Secure
    Set-Cookie: <cookie-name>=<cookie-value>; HttpOnly

    Set-Cookie: <cookie-name>=<cookie-value>; SameSite=Strict
    Set-Cookie: <cookie-name>=<cookie-value>; SameSite=Lax
    Set-Cookie: <cookie-name>=<cookie-value>; SameSite=None

    // Multiple attributes are also possible, for example:
    Set-Cookie: <cookie-name>=<cookie-value>; Domain=<domain-value>; Secure; HttpOnly

Attributes
----------

`<cookie-name>=<cookie-value>`  
A cookie begins with a name-value pair:

-   A `<cookie-name>` can be any US-ASCII characters, except control characters, spaces, or tabs. It also must not contain a separator character like the following: `( ) < > @ , ; : \ " / [ ] ? = { }`.
-   A `<cookie-value>` can optionally be wrapped in double quotes and include any US-ASCII characters excluding control characters, [Whitespace](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace), double quotes, comma, semicolon, and backslash. **Encoding**: Many implementations perform URL encoding on cookie values, however it is not required per the RFC specification. It does help satisfying the requirements about which characters are allowed for &lt;cookie-value&gt; though.
-   `__Secure-`: Cookies names starting with` __Secure-` (dash is part of the prefix) must be set with the `secure` flag from a secure page (HTTPS).
-   `__Host-`: Cookies with names starting with `__Host-` must be set with the `secure` flag, must be from a secure page (HTTPS), must not have a domain specified (and therefore aren't sent to subdomains) and the path must be `/`.

 `Expires=<date>` <span class="inlineIndicator optional optionalInline">Optional</span>   
The maximum lifetime of the cookie as an HTTP-date timestamp. See [`Date`](date) for the required formatting.

If unspecified, the cookie becomes a **session cookie**. A session finishes when the client shuts down, and session cookies will be removed.

**Warning:** Many web browsers have a *session restore* feature that will save all tabs and restore them next time the browser is used. Session cookies will also be restored, as if the browser was never closed.

When an Expires date is set, the deadline is relative to the *client* the cookie is being set on, not the server.

 `Max-Age=<number> `<span class="inlineIndicator optional optionalInline">Optional</span>   
Number of seconds until the cookie expires. A zero or negative number will expire the cookie immediately. If both `Expires` and `Max-Age` are set, `Max-Age` has precedence.

 `Domain=<domain-value>` <span class="inlineIndicator optional optionalInline">Optional</span>   
Host to which the cookie will be sent.

-   If omitted, defaults to the host of the current document URL, not including subdomains.
-   Contrary to earlier specifications, leading dots in domain names (`.example.com`) are ignored.
-   Multiple host/domain values are *not* allowed, but if a domain *is* specified, then subdomains are always included.

 `Path=<path-value>` <span class="inlineIndicator optional optionalInline">Optional</span>   
A path that must exist in the requested URL, or the browser won't send the `Cookie` header.

The forward slash (`/`) character is interpreted as a directory separator, and subdirectories will be matched as well: for `Path=/docs`, `/docs`, `/docs/Web/`, and `/docs/Web/HTTP` will all match.

 `Secure` <span class="inlineIndicator optional optionalInline">Optional</span>   
Cookie is only sent to the server when a request is made with the `https:` scheme (except on localhost), and therefore is more resistent to [man-in-the-middle](https://wiki.developer.mozilla.org/en-US/docs/Glossary/MitM) attacks.

**Note:** Do not assume that `Secure` prevents all access to sensitive information in cookies (session keys, login details, etc.). Cookies with this attribute can still be read/modified with access to the client's hard disk, or from JavaScript if the `HttpOnly` cookie attribute is not set.

**Note:** Insecure sites (`http:`) can't set cookies with the `Secure` attribute (since Chrome 52 and Firefox 52). For Firefox, the `https:` requirements are ignored when the `Secure` attribute is set by localhost (since Firefox 75).

 `HttpOnly` <span class="inlineIndicator optional optionalInline">Optional</span>   
Forbids JavaScript from accessing the cookie, for example, through the [`Document.cookie`](https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie) property. Note that a cookie that has been created with HttpOnly will still be sent with JavaScript-initiated requests, e.g. when calling [`XMLHttpRequest.send()`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/send) or [`fetch()`](https://developer.mozilla.org/en-US/docs/Web/API/Fetch). This mitigates attacks against cross-site scripting ([XSS](https://developer.mozilla.org/en-US/docs/Glossary/XSS)).

 `SameSite=<samesite-value>` <span class="inlineIndicator optional optionalInline">Optional</span>   
-   `Strict`: The browser sends the cookie only for same-site requests (that is, requests originating from the same site that set the cookie). If the request originated from a different URL than the current one, no cookies with the `SameSite=Strict` attribute are sent.
-   `Lax`: The cookie is withheld on cross-site subrequests, such as calls to load images or frames, but is sent when a user navigates to the URL from an external site, such as by following a link.
-   `None`: The browser sends the cookie with both cross-site and same-site requests.

Asserts that a cookie must not be sent with cross-origin requests, providing some protection against cross-site request forgery attacks ([CSRF](https://developer.mozilla.org/en-US/docs/Glossary/CSRF)).

Browsers are migrating to have [cookies default to `SameSite=Lax`](https://www.chromestatus.com/feature/5088147346030592). If a cookie is needed to be sent cross-origin, opt out of the `SameSite` restriction using the `None` value. The `None` value requires the [`Secure`](#Secure) attribute.

Examples
--------

### Session cookie

**Session cookies** are removed when the client shuts down. Cookies are session cookies if they don't specify the `Expires` or `Max-Age` attributes.

    Set-Cookie: sessionId=38afes7a8

### Permanent cookie

Instead of expiring when the client is closed, **permanent cookies** expire at a specific date (`Expires`) or after a specific length of time (`Max-Age`).

    Set-Cookie: id=a3fWa; Expires=Wed, 21 Oct 2015 07:28:00 GMT

    Set-Cookie: id=a3fWa; Max-Age=2592000

### Invalid domains

A cookie for a domain that does not include the server that set it [should be rejected by the user agent](https://tools.ietf.org/html/rfc6265#section-4.1.2.3).

The following cookie will be rejected if set by a server hosted on `originalcompany.com`:

    Set-Cookie: qwerty=219ffwef9w0f; Domain=somecompany.co.uk

A cookie for a sub domain of the serving domain will be rejected.

The following cookie will be rejected if set by a server hosted on `example.com`:

    Set-Cookie: sessionId=e8bb43229de9; Domain=foo.example.com

### Cookie prefixes

Cookies names prefixed with `__Secure-` or `__Host-` can be used only if they are set with the `secure` attribute from a secure (HTTPS) origin.

In addition, cookies with the `__Host-` prefix must have a path of `/` (meaning any path at the host) and must not have a `Domain` attribute.

For clients that don't implement cookie prefixes, you cannot count on these additional assurances, and prefixed cookies will always be accepted.

    // Both accepted when from a secure origin (HTTPS)
    Set-Cookie: __Secure-ID=123; Secure; Domain=example.com
    Set-Cookie: __Host-ID=123; Secure; Path=/

    // Rejected due to missing Secure attribute
    Set-Cookie: __Secure-id=1

    // Rejected due to the missing Path=/ attribute
    Set-Cookie: __Host-id=1; Secure

    // Rejected due to setting a Domain
    Set-Cookie: __Host-id=1; Secure; Path=/; Domain=example.com

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc6265#section-4.1">RFC 6265, section 4.1: Set-Cookie</a></td><td>HTTP State Management Mechanism</td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/draft-ietf-httpbis-rfc6265bis-05">draft-ietf-httpbis-rfc6265bis-05</a></td><td>Cookie Prefixes, Same-Site Cookies, and Strict Secure Cookies</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Set-Cookie`

Yes

12

Yes

Yes

Yes

Yes

`HttpOnly`

1

12

3

9

11

5

`Max-Age`

Yes

12

Yes

8

Yes

Yes

`SameSite`

51

16

60

No

39

13

 13   
Safari 13 on macOS 10.14 (Mojave), treats `SameSite=None` and invalid values as `Strict`. This is fixed in version 10.15 (Catalina) and later.

12   
Treats `SameSite=None` and invalid values as `Strict` in macOS before 10.15 Catalina. See [bug 198181](https://webkit.org/b/198181).

`SameSite`: `SameSite=Lax`

51

16

60

No

39

12

`SameSite`: Defaults to `Lax`

80

80

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `network.cookie.sameSite.laxByDefault` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

67

No

`SameSite`: `SameSite=None`

51

16

60

No

39

13

 13   
Not supported prior to macOS before version 10.15 (Catalina).

`SameSite`: `SameSite=Strict`

51

16

60

No

39

12

`SameSite`: Secure context required

80

80

69

Disabled

69

Disabled

Disabled From version 69: this feature is behind the `network.cookie.sameSite.noneRequiresSecure` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

No

67

No

Cookie prefixes

49

79

50

No

36

Yes

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Set-Cookie`

Yes

Yes

Yes

Yes

Yes

Yes

`HttpOnly`

37

Yes

4

Yes

4

Yes

`Max-Age`

Yes

Yes

Yes

Yes

Yes

Yes

`SameSite`

51

51

60

41

13

 13  
12.2   
Treats `SameSite=None` and invalid values as `Strict` in iOS before 13. See [bug 198181](https://webkit.org/b/198181).

5.0

`SameSite`: `SameSite=Lax`

51

51

60

41

12.2

5.0

`SameSite`: Defaults to `Lax`

80

80

No

No

No

No

`SameSite`: `SameSite=None`

51

51

60

41

13

5.0

`SameSite`: `SameSite=Strict`

51

51

60

41

12.2

5.0

`SameSite`: Secure context required

80

80

No

No

No

No

Cookie prefixes

49

49

50

36

Yes

5.0

Compatibility notes
-------------------

-   Starting with Chrome 52 and Firefox 52, insecure sites (`http:`) can't set cookies with the `Secure` attribute anymore.

See also
--------

-   [HTTP cookies](../cookies)
-   [`Cookie`](cookie)
-   [`Document.cookie`](https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie</a>
