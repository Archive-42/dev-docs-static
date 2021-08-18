If-Match
========

The `If-Match` HTTP request header makes the request conditional. For [`GET`](../methods/get) and [`HEAD`](../methods/head) methods, the server will send back the requested resource only if it matches one of the listed `ETags`. For [`PUT`](../methods/put) and other non-safe methods, it will only upload the resource in this case.

The comparison with the stored [`ETag`](etag) uses the *strong comparison algorithm*, meaning two files are considered identical byte to byte only. If a listed `ETag` has the `W/` prefix indicating a weak entity tag, it will never match under this comparison algorithm.

There are two common use cases:

-   For [`GET`](../methods/get) and [`HEAD`](../methods/head) methods, used in combination with a [`Range`](range) header, it can guarantee that the new ranges requested comes from the same resource than the previous one. If it doesn't match, then a [`416`](../status/416) (Range Not Satisfiable) response is returned.
-   For other methods, and in particular for [`PUT`](../methods/put), `If-Match` can be used to prevent the [lost update problem](https://www.w3.org/1999/04/Editing/#3.1). It can check if the modification of a resource that the user wants to upload will not override another change that has been done since the original resource was fetched. If the request cannot be fulfilled, the [`412`](../status/412) (Precondition Failed) response is returned.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    If-Match: <etag_value>
    If-Match: <etag_value>, <etag_value>, …

Directives
----------

&lt;etag\_value&gt;  
Entity tags uniquely representing the requested resources. They are a string of ASCII characters placed between double quotes (like `"675af34563dc-tr34"`). They may be prefixed by `W/` to indicate that they are "weak", i.e. that they represent the resource semantically, but not byte-for-byte. However, in an `If-Match` header, weak entity tags will never match.

`*`  
The asterisk is a special value representing any resource.

Examples
--------

    If-Match: "bfc13a64729c4290ef5b2c2730249c88ca92d82d"

    If-Match: "67ab43", "54ed21", "7892dd"

    If-Match: *

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7232#section-3.1">RFC 7232, section 3.1: If-Match</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Conditional Requests</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`If-Match`

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

`If-Match`

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
-   [`If-None-Match`](if-none-match)
-   [`416`](../status/416)` Range Not Satisfiable`
-   [`412`](../status/412)` Precondition Failed`

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/If-Match$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/If-Match" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/If-Match</a>
