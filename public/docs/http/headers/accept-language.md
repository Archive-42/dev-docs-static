Accept-Language
===============

The `Accept-Language` request HTTP header advertises which languages the client is able to understand, and which locale variant is preferred. (By languages, we mean natural languages, such as English, and not programming languages.) Using [content negotiation](../content_negotiation), the server then selects one of the proposals, uses it and informs the client of its choice with the [`Content-Language`](content-language) response header. Browsers set adequate values for this header according to their user interface language and even if a user can change it, this happens rarely (and is frowned upon as it leads to fingerprinting).

This header is a hint to be used when the server has no way of determining the language via another way, like a specific URL, that is controlled by an explicit user decision. It is recommended that the server never overrides an explicit decision. The content of the `Accept-Language` is often out of the control of the user (like when traveling and using an Internet Cafe in a different country); the user may also want to visit a page in another language than the locale of their user interface.

If the server cannot serve any matching language, it can theoretically send back a [`406`](../status/406) (Not Acceptable) error code. But, for a better user experience, this is rarely done and more common way is to ignore the `Accept-Language` header in this case.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_request_header">CORS-safelisted request header</a></td><td>yes, with the additional restriction that values can only be <code>0-9</code>, <code>A-Z</code>, <code>a-z</code>, space or <code>*,-.;=</code>.</td></tr></tbody></table>

Syntax
------

    Accept-Language: <language>
    Accept-Language: *

    // Multiple types, weighted with the quality value syntax:
    Accept-Language: fr-CH, fr;q=0.9, en;q=0.8, de;q=0.7, *;q=0.5

Directives
----------

`<language>`  
A language tag (which is sometimes referred to as a "locale identifier"). This consists of a 2-3 letter base language tag representing the language, optionally followed by additional subtags separated by `'-'`. The most common extra information is the country or region variant (like `'en-US'` or `'fr-CA'`) or the type of alphabet to use (like `'sr-Latn'`). Other variants like the type of orthography (`'de-DE-1996'`) are usually not used in the context of this header.

`*`  
Any language; `'*'` is used as a wildcard.

 `;q=` (q-factor weighting)  
Any value placed in an order of preference expressed using a relative [quality value](https://developer.mozilla.org/en-US/docs/Glossary/Quality_values) called *weight*.

Examples
--------

    Accept-Language: de

    Accept-Language: de-CH

    Accept-Language: en-US,en;q=0.5

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-5.3.5">RFC 7231, section 5.3.5: Accept-Language</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Context</td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/bcp47">BCP 47</a></td><td>Tags for the Identification of Language</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Accept-Language`

Yes

12

Yes

Yes

Yes

Yes

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Accept-Language`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   HTTP [content negotiation](../content_negotiation)
-   Header with the result of the content negotiation: [`Content-Language`](content-language)
-   Other similar headers: [`TE`](te), [`Accept-Encoding`](accept-encoding), [`Accept-Charset`](accept-charset), [`Accept`](accept)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Language$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Language" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Language</a>
