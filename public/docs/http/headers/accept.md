Accept
======

The `Accept` request HTTP header advertises which content types, expressed as [MIME types](../basics_of_http/mime_types), the client is able to understand. Using [content negotiation](../content_negotiation), the server then selects one of the proposals, uses it and informs the client of its choice with the [`Content-Type`](content-type) response header. Browsers set adequate values for this header depending on the context where the request is done: when fetching a CSS stylesheet a different value is set for the request than when fetching an image, video or a script.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_request_header">CORS-safelisted request header</a></td><td>yes, with the additional restriction that values can't contain a <em>CORS-unsafe request header byte</em>: 0x00-0x1F (except 0x09 (HT)), <code>"():&lt;&gt;?@[\]{}</code>, and 0x7F (DEL).</td></tr></tbody></table>

Syntax
------

    Accept: <MIME_type>/<MIME_subtype>
    Accept: <MIME_type>/*
    Accept: */*

    // Multiple types, weighted with the quality value syntax:
    Accept: text/html, application/xhtml+xml, application/xml;q=0.9, image/webp, */*;q=0.8

Directives
----------

`<MIME_type>/<MIME_subtype>`  
A single, precise [MIME type](../basics_of_http/mime_types), like `text/html`.

`<MIME_type>/*`  
A MIME type, but without any subtype. `image/*` will match `image/png`, `image/svg`, `image/gif` and any other image types.

`*/*`  
Any MIME type

 `;q=` (q-factor weighting)  
Any value used is placed in an order of preference expressed using relative [quality value](https://developer.mozilla.org/en-US/docs/Glossary/Quality_values) called the *weight*.

Examples
--------

    Accept: text/html

    Accept: image/*

    // General default
    Accept: */*

    // Default for navigation requests
    Accept: text/html, application/xhtml+xml, application/xml;q=0.9, */*;q=0.8

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-5.3.2">RFC 7231, section 5.3.2: Accept</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Context</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Accept`

Yes

12

Yes

 Yes   
In Firefox 66, the default `Accept` header value changed to `*/*`.

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

`Accept`

Yes

Yes

Yes

 Yes   
In Firefox 66, the default `Accept` header value changed to `*/*`.

Yes

Yes

Yes

See also
--------

-   HTTP [content negotiation](../content_negotiation)
-   Header with the result of the content negotiation: [`Content-Type`](content-type)
-   Other similar headers: [`TE`](te), [`Accept-Encoding`](accept-encoding), [`Accept-Charset`](accept-charset), [`Accept-Language`](accept-language)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept</a>
