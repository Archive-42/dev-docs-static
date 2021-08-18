Set-Cookie: SameSite
====================

The `SameSite` attribute of the [`Set-Cookie`](../set-cookie) HTTP response header allows you to declare if your cookie should be restricted to a first-party or same-site context.

Values
------

The `SameSite` attribute accepts three values:

### `Lax`

Cookies are allowed to be sent with top-level navigations and will be sent along with GET request initiated by third party website. This is the default value in modern browsers.

### `Strict`

Cookies will only be sent in a first-party context and not be sent along with requests initiated by third party websites.

### `None`

Cookies will be sent in all contexts, i.e sending cross-origin is allowed.

`None` used to be the default value, but recent browser versions made `Lax` the default value to have reasonably robust defense against some classes of cross-site request forgery ([CSRF](https://developer.mozilla.org/en-US/docs/Glossary/CSRF)) attacks.

`None` requires the [`Secure`](../set-cookie#Secure) attribute in latest browser versions. See below for more information.

Fixing common warnings
----------------------

### `SameSite=None` requires `Secure`

The following warning might appear in your console:

> Some cookies are misusing the “sameSite“ attribute, so it won’t work as expected.  
> Cookie “*myCookie*” rejected because it has the “sameSite=none” attribute but is missing the “secure” attribute.

The warning appears because any cookie that requests `SameSite=None` but is not marked `Secure` will be rejected.

    Set-Cookie: flavor=choco; SameSite=None

To fix this, you will have to add the `Secure` attribute to your `SameSite=None` cookies.

    Set-Cookie: flavor=choco; SameSite=None; Secure

A [`Secure`](#Secure) cookie is only sent to the server with an encrypted request over the HTTPS protocol. Note that insecure sites (`http:`) can't set cookies with the `Secure` directive.

### Cookies without `SameSite` default to `SameSite=Lax`

Recent versions of modern browsers provide a more secure default for `SameSite` to your cookies and so the following message might appear in your console:

> Some cookies are misusing the “sameSite“ attribute, so it won’t work as expected.  
> Cookie “*myCookie*” has “sameSite” policy set to “lax” because it is missing a “sameSite” attribute, and “sameSite=lax” is the default value for this attribute.

The warning appears because the `SameSite` policy for a cookie has not specified explicitly:

    Set-Cookie: flavor=choco

While you could rely on modern browsers to apply `SameSite=Lax` automatically, you should rather specify it explicitly to clearly communicate your intent which `SameSite` policy applies to your cookie. This will also improve the experience across browsers as not all of them default to `Lax` yet.

    Set-Cookie: flavor=choco; SameSite=Lax

Example:
--------

    RewriteEngine on
    RewriteBase "/"
    RewriteCond "%{HTTP_HOST}"       "^example\.org$" [NC]
    RewriteRule "^(.*)"              "https://www.example.org/index.html" [R=301,L,QSA]
    RewriteRule "^(.*)\.ht$"         "index.php?nav=$1 [NC,L,QSA,CO=RewriteRule;01;https://www.example.org;30/;SameSite=None;Secure]
    RewriteRule "^(.*)\.htm$"        "index.php?nav=$1 [NC,L,QSA,CO=RewriteRule;02;https://www.example.org;30/;SameSite=None;Secure]
    RewriteRule "^(.*)\.html$"       "index.php?nav=$1 [NC,L,QSA,CO=RewriteRule;03;https://www.example.org;30/;SameSite=None;Secure]
    [...]
    RewriteRule "^admin/(.*)\.html$" "admin/index.php?nav=$1 [NC,L,QSA,CO=RewriteRule;09;https://www.example.org:30/;SameSite=Strict;Secure]

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

[`Set-Cookie`](../set-cookie)

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

[`Set-Cookie`](../set-cookie)

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

See also
--------

-   [HTTP cookies](../../cookies)
-   [`Cookie`](../cookie)
-   [`Document.cookie`](https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie/SameSite$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie/SameSite" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie/SameSite</a>
