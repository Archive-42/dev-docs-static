Warning
=======

**Note**: The `Warning` header is soon to be deprecated; see [Warning (https://github.com/httpwg/http-core/issues/139)](https://github.com/httpwg/http-core/issues/139) and [Warning: header & stale-while-revalidate (https://github.com/whatwg/fetch/issues/913)](https://github.com/whatwg/fetch/issues/913) for more details.

The `Warning` general HTTP header contains information about possible problems with the status of the message. More than one `Warning` header may appear in a response.

`Warning` header fields can in general be applied to any message, however some warn-codes are specific to caches and can only be applied to response messages.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/General_header">General header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Warning: <warn-code> <warn-agent> <warn-text> [<warn-date>]

Directives
----------

&lt;warn-code&gt;  
A three-digit warning number. The first digit indicates whether the `Warning` is required to be deleted from a stored response after validation.

-   `1xx` warn-codes describe the freshness or validation status of the response and will be deleted by a cache after deletion.
-   `2xx` warn-codes describe some aspect of the representation that is not rectified by a validation and won't be deleted by a cache after validation unless a full response is sent.

&lt;warn-agent&gt;  
The name or pseudonym of the server or software adding the `Warning` header (might be "-" when the agent is unknown).

&lt;warn-text&gt;  
Advisory text describing the error.

&lt;warn-date&gt;  
Optional. If more than one `Warning` header is sent, include a date that matches the [`Date`](date) header.

Warning codes
-------------

The [HTTP Warn Codes registry at iana.org](http://www.iana.org/assignments/http-warn-codes/http-warn-codes.xhtml) defines the namespace for warn codes.

<table><thead><tr class="header"><th>Code</th><th>Text</th><th>Description</th></tr></thead><tbody><tr class="odd"><td>110</td><td>Response is Stale</td><td>A response provided by a cache is stale (the expiration time set for it has passed).</td></tr><tr class="even"><td>111</td><td>Revalidation Failed</td><td>An attempt to validate the response failed, due to an inability to reach the server.</td></tr><tr class="odd"><td>112</td><td>Disconnected Operation</td><td>The cache is disconnected from the rest of the network.</td></tr><tr class="even"><td>113</td><td>Heuristic Expiration</td><td>Sent If a cache heuristically chose a freshness lifetime greater than 24 hours and the response's age is greater than 24 hours.</td></tr><tr class="odd"><td>199</td><td>Miscellaneous Warning</td><td>Arbitrary, non-specific warning</td></tr><tr class="even"><td>214</td><td>Transformation Applied</td><td>Added by a proxy if it applies any transformation to the representation, such as changing the content-coding, media-type or the like.</td></tr><tr class="odd"><td>299</td><td>Miscellaneous Persistent Warning</td><td>Same as 199, but indicating a persistent warning</td></tr></tbody></table>

Examples
--------

    Warning: 110 anderson/1.3.37 "Response is stale"

    Date: Wed, 21 Oct 2015 07:28:00 GMT 
    Warning: 112 - "cache down" "Wed, 21 Oct 2015 07:28:00 GMT"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7234#section-5.5">RFC 7234, section 5.5: Warning</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Caching</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Warning`

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

`Warning`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Date`](date)
-   [HTTP response status codes](../status)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Warning$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Warning" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Warning</a>
