If-None-Match
=============

The `If-None-Match` HTTP request header makes the request conditional. For [`GET`](../methods/get) and [`HEAD`](../methods/head) methods, the server will send back the requested resource, with a [`200`](../status/200) status, only if it doesn't have an [`ETag`](etag) matching the given ones. For other methods, the request will be processed only if the eventually existing resource's [`ETag`](etag) doesn't match any of the values listed.

When the condition fails for [`GET`](../methods/get) and [`HEAD`](../methods/head) methods, then the server must return HTTP status code 304 (Not Modified). For methods that apply server-side changes, the status code 412 (Precondition Failed) is used. Note that the server generating a 304 response MUST generate any of the following header fields that would have been sent in a 200 (OK) response to the same request: Cache-Control, Content-Location, Date, ETag, Expires, and Vary.

The comparison with the stored [`ETag`](etag) uses the *weak comparison algorithm*, meaning two files are considered identical if the content is equivalent — they don't have to be identical byte for byte. For example, two pages that differ by the date of generation in the footer would still be considered as identical.

When used in combination with [`If-Modified-Since`](if-modified-since), `If-None-Match` has precedence (if the server supports it).

There are two common use cases:

-   For [`GET`](../methods/get) and [`HEAD`](../methods/head) methods, to update a cached entity that has an associated [`ETag`](etag).
-   For other methods, and in particular for [`PUT`](../methods/put), `If-None-Match` used with the `*` value can be used to save a file not known to exist, guaranteeing that another upload didn't happen before, losing the data of the previous put; this problem is a variation of the [lost update problem](https://www.w3.org/1999/04/Editing/#3.1).

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    If-None-Match: "<etag_value>"
    If-None-Match: "<etag_value>", "<etag_value>", …
    If-None-Match: *

Directives
----------

&lt;etag\_value&gt;  
Entity tags uniquely representing the requested resources. They are a string of ASCII characters placed between double quotes (Like `"675af34563dc-tr34"`) and may be prefixed by `W/` to indicate that the weak comparison algorithm should be used (This is useless with `If-None-Match` as it only uses that algorithm).

`*`  
The asterisk is a special value representing any resource. They are only useful when uploading a resource, usually with [`PUT`](../methods/put), to check if another resource with the identity has already been uploaded before.

Examples
--------

    If-None-Match: "bfc13a64729c4290ef5b2c2730249c88ca92d82d"

    If-None-Match: W/"67ab43", "54ed21", "7892dd"

    If-None-Match: *

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7232#section-3.2">RFC 7232, section 3.2: If-None-Match</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Conditional Requests</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`If-None-Match`

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

`If-None-Match`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`ETag`](etag)
-   [`If-Unmodified-Since`](if-unmodified-since)
-   [`If-Modified-Since`](if-modified-since)
-   [`If-Match`](if-match)
-   [`304`](../status/304)` Not Modified`
-   [`412`](../status/412)` Precondition Failed`

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/If-None-Match$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/If-None-Match" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/If-None-Match</a>
