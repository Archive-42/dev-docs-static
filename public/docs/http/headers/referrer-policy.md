Referrer-Policy
===============

The `Referrer-Policy` [HTTP header](https://developer.mozilla.org/en-US/docs/Glossary/HTTP_header) controls how much [referrer information](https://developer.mozilla.org/en-US/docs/Web/Security/Referer_header:_privacy_and_security_concerns) (sent via the [`Referer`](referer) header) should be included with requests.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

The original header name [`Referer`](referer) is a misspelling of the word "referrer". The `Referrer-Policy` header does not share this misspelling.

    Referrer-Policy: no-referrer
    Referrer-Policy: no-referrer-when-downgrade
    Referrer-Policy: origin
    Referrer-Policy: origin-when-cross-origin
    Referrer-Policy: same-origin
    Referrer-Policy: strict-origin
    Referrer-Policy: strict-origin-when-cross-origin
    Referrer-Policy: unsafe-url

Directives
----------

`no-referrer`  
The [`Referer`](referer) header will be omitted entirely. No referrer information is sent along with requests.

 `no-referrer-when-downgrade` (default)  
This is the default behavior if no policy is specified, or if the provided value is invalid. The [origin](https://developer.mozilla.org/en-US/docs/Glossary/origin), [path](https://developer.mozilla.org/en-US/docs/Glossary/path), and [querystring](https://developer.mozilla.org/en-US/docs/Glossary/querystring) of the URL are sent as a referrer when the protocol security level stays the same (HTTP→HTTP, HTTPS→HTTPS) or improves (HTTP→HTTPS), but isn't sent to less secure destinations (HTTPS→HTTP).

There is effort from browsers in moving to a stricter default value, namely `strict-origin-when-cross-origin` (see <https://github.com/whatwg/fetch/pull/952>), consider using this value (or a stricter one), if possible, when changing the Referrer-Policy.

`origin`  
Only send the [origin](https://developer.mozilla.org/en-US/docs/Glossary/origin) of the document as the referrer.  
For example, a document at `https://example.com/page.html` will send the referrer `https://example.com/`.

`origin-when-cross-origin`  
Send the origin, path, and query string when performing a [same-origin](https://developer.mozilla.org/en-US/docs/Glossary/Same-origin_policy) request, but only send the origin of the document for other cases.

`same-origin`  
A referrer will be sent for [same-site origins](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy), but cross-origin requests will send no referrer information.

`strict-origin`  
Only send the origin of the document as the referrer when the protocol security level stays the same (HTTPS→HTTPS), but don't send it to a less secure destination (HTTPS→HTTP).

`strict-origin-when-cross-origin`  
Send the origin, path, and querystring when performing a same-origin request, only send the origin when the protocol security level stays the same while performing a cross-origin request (HTTPS→HTTPS), and send no header to any less-secure destinations (HTTPS→HTTP).

`unsafe-url`  
Send the origin, path, and query string when performing any request, regardless of security.

This policy will leak potentially-private information from HTTPS resource URLs to insecure origins. Carefully consider the impact of this setting.

Integration with HTML
---------------------

You can also set referrer policies inside HTML. For example, you can set the referrer policy for the entire document with a [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) element with a [name](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta#attr-name) of `referrer`:

    <meta name="referrer" content="origin">

Or set it for individual requests with the `referrerpolicy` attribute on [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a), [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area), [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img), [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe), [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script), or [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) elements:

    <a href="http://example.com" referrerpolicy="origin">

Alternatively, a `noreferrer` [link relation](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types) on an `a`, `area`, or `link` element can be set:

    <a href="http://example.com" rel="noreferrer">

As seen above, the `noreferrer` link relation is written without a dash — `noreferrer`. When the referrer policy is specified for the entire document with a [`<meta>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/meta) element, it's written *with* a dash: `<meta name="referrer" content="no-referrer">`.

Integration with CSS
--------------------

CSS can fetch resources referenced from stylesheets. These resources follow a referrer policy as well:

-   External CSS stylesheets use the default policy (`no-referrer-when-downgrade`), unless it's overwritten via a `Referrer-Policy` HTTP header on the CSS stylesheet’s response.
-   For [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) elements or [`style` attributes](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/style), the owner document's referrer policy is used.

Examples
--------

Policy

Document

Navigation to

Referrer

`no-referrer`

https://example.com/page

*anywhere*

*(no referrer)*

`no-referrer-when-downgrade`

https://example.com/page

https://example.com/otherpage

https://example.com/page

https://mozilla.org

https://example.com/page

**http**://example.org

*(no referrer)*

`origin`

https://example.com/page

*anywhere*

https://example.com/

`origin-when-cross-origin`

https://example.com/page

https://example.com/otherpage

https://example.com/page

https://mozilla.org

https://example.com/

**http**://example.com/page

https://example.com/

`same-origin`

https://example.com/page

https://example.com/otherpage

https://example.com/page

https://mozilla.org

*(no referrer)*

`strict-origin`

https://example.com/page

https://mozilla.org

https://example.com/

**http**://example.org

*(no referrer)*

**http**://example.com/page

*anywhere*

http://example.com/

`strict-origin-when-cross-origin`

https://example.com/page

https://example.com/otherpage

https://example.com/page

https://mozilla.org

https://example.com/

**http**://example.org

*(no referrer)*

`unsafe-url`

https://example.com/page?q=123

*anywhere*

https://example.com/page?q=123

### Specifying a fallback policy

If you want to specify a fallback policy in any case the desired policy hasn't got wide enough browser support, use a comma-separated list with the desired policy specified last:

    Referrer-Policy: no-referrer, strict-origin-when-cross-origin

In the above scenario, `no-referrer` will only be used if `strict-origin-when-cross-origin` is not supported by the browser.

Specifying multiple values is only supported in the `Referrer-Policy` HTTP header, and not in the `referrerpolicy` attribute.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webappsec-referrer-policy/#referrer-policy-header">Referrer Policy</a></td><td>Editor's draft</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Referrer-Policy`

56

79

50

No

43

11.1

same-origin

61

79

52

No

48

11.1

strict-origin

61

79

52

No

48

11.1

strict-origin-when-cross-origin

61

79

52

No

48

11.1

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Referrer-Policy`

56

56

50

43

No

7.2

same-origin

61

61

52

45

No

7.2

strict-origin

61

61

52

45

No

7.2

strict-origin-when-cross-origin

61

61

52

45

No

7.2

-   From version 53 onwards, Gecko has a pref available in `about:config` to allow users to set their default `Referrer-Policy` — <span class="quote"> `network.http.referer.userControlPolicy`.</span>
-   From version 59 onwards (See [\#587523](https://bugzilla.mozilla.org/show_bug.cgi?id=587523)), this has been replaced by `network.http.referer.defaultPolicy` and `network.http.referer.defaultPolicy.pbmode`.

Possible values are:

-   0 — `no-referrer`
-   1 — `same-origin`
-   2 — `strict-origin-when-cross-origin`
-   3 — `no-referrer-when-downgrade` (the default)

See also
--------

-   [HTTP referer on Wikipedia](https://en.wikipedia.org/wiki/HTTP_referer)
-   When using [Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API): [`Request.referrerPolicy`](https://developer.mozilla.org/en-US/docs/Web/API/Request/referrerPolicy)
-   The obsolete <span style="white-space: nowrap;">[`Content-Security-Policy`](content-security-policy)</span> [`referrer`](content-security-policy/referrer) directive.
-   [Same-origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy)
-   [Tighter Control Over Your Referrers – Mozilla Security Blog](https://blog.mozilla.org/security/2015/01/21/meta-referrer/)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Referrer-Policy</a>
