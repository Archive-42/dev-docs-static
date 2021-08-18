Accept-Charset
==============

The `Accept-Charset` request HTTP header advertises which [character encodings](https://developer.mozilla.org/en-US/docs/Glossary/character_encoding) the client understands. Using [content negotiation](../content_negotiation), the server selects one of the encodings, uses it, and informs the client of its choice within the [`Content-Type`](content-type) response header, usually in a `charset=` parameter. Browsers usually don't send this header, as the default value for each resource is usually correct and transmitting it would allow [fingerprinting](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Privacy/Tracking_Protection).

If the server cannot serve any character encoding from this request header, it can theoretically send back a [`406 Not Acceptable`](../status/406) error code. But for a better user experience, this is rarely done and the `Accept-Charset` header is ignored.

In early versions of HTTP/1.1, a default character encoding was defined: ISO-8859-1. This is no longer recommended, and now each content-type may have its own default.

UTF-8 is now well-supported and the overwhelmingly preferred character encoding. To [guarantee better privacy through less configuration-based entropy](https://www.eff.org/deeplinks/2010/01/primer-information-theory-and-privacy), all browsers omit the `Accept-Charset` header: Internet Explorer 8+, Safari 5+, Opera 11+, Firefox 10+ and Chrome 27+ no longer send it.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Accept-Charset: <charset>

    // Multiple types, weighted with the quality value syntax:
    Accept-Charset: utf-8, iso-8859-1;q=0.5

Directives
----------

`<charset>`  
A character encoding name, like `utf-8` or `iso-8859-15.`

`*`  
Any charset not mentioned elsewhere in the header; `*` is used as a wildcard.

`;q=<weight>`  
Any encoding is placed in an order of preference, expressed using a relative [quality value](https://developer.mozilla.org/en-US/docs/Glossary/quality_values) called the *weight*.

Examples
--------

    Accept-Charset: iso-8859-1

    Accept-Charset: utf-8, iso-8859-1;q=0.5

    Accept-Charset: utf-8, iso-8859-1;q=0.5, *;q=0.1

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-5.3.3">RFC 7231, section 5.3.3: Accept-Charset</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Context</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Accept-Charset`

? — 27

No

? — 10

? — 8

? — 11

? — 5

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Accept-Charset`

? — ?

? — 27

? — 10

? — 11

? — 4.2

? — 1.5

See also
--------

-   HTTP [content negotiation](../content_negotiation)
-   [Accept-Charset is no more](https://hsivonen.fi/accept-charset/)
-   Header with the result of the content negotiation: [`Content-Type`](content-type)
-   Other similar headers: [`TE`](te), [`Accept-Encoding`](accept-encoding), [`Accept-Language`](accept-language), [`Accept`](accept)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Charset$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Charset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Charset</a>
