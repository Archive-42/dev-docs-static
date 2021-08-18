ETag
====

The `ETag` HTTP response header is an identifier for a specific version of a resource. It lets caches be more efficient and save bandwidth, as a web server does not need to resend a full response if the content has not changed. Additionally, etags help prevent simultaneous updates of a resource from overwriting each other (["mid-air collisions"](#Caching_of_unchanged_resources)).

If the resource at a given URL changes, a new `Etag` value *must* be generated. A comparison of them can determine whether two representations of a resource are the same. Etags are therefore similar to fingerprints, and might also be used for tracking purposes by some servers. They might also be set to persist indefinitely by a tracking server.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    ETag: W/"<etag_value>"
    ETag: "<etag_value>"

Directives
----------

 `W/` <span class="inlineIndicator optional optionalInline">Optional</span>   
`'W/'` (case-sensitive) indicates that a [weak validator](../conditional_requests#Weak_validation) is used. Weak etags are easy to generate, but are far less useful for comparisons. Strong validators are ideal for comparisons but can be very difficult to generate efficiently. Weak `ETag` values of two representations of the same resources might be semantically equivalent, but not byte-for-byte identical. This means weak etags prevent caching when [byte range requests](accept-ranges) are used, but strong etags mean range requests can still be cached.

"&lt;etag\_value&gt;"  
Entity tag uniquely representing the requested resource. They are a string of ASCII characters placed between double quotes, like `"675af34563dc-tr34"`. The method by which `ETag` values are generated is not specified. Often, a hash of the content, a hash of the last modification timestamp, or just a revision number is used. For example, MDN uses a hexadecimal hash of the wiki article content.

Examples
--------

    ETag: "33a64df551425fcc55e4d42a148795d9f25f89d4"
    ETag: W/"0815"

### Avoiding mid-air collisions

With the help of the `ETag` and the [`If-Match`](if-match) headers, you can detect mid-air edit collisions.

For example, when editing MDN, the current wiki content is hashed and put into an `Etag` in the response:

    ETag: "33a64df551425fcc55e4d42a148795d9f25f89d4"

When saving changes to a wiki page (posting data), the [`POST`](../methods/post) request will contain the [`If-Match`](if-match) header containing the `ETag` values to check freshness against.

    If-Match: "33a64df551425fcc55e4d42a148795d9f25f89d4"

If the hashes don't match, it means that the document has been edited in-between and a [`412`](../status/412) `Precondition Failed` error is thrown.

### Caching of unchanged resources

Another typical use of the `ETag` header is to cache resources that are unchanged. If a user visits a given URL again (that has an `ETag` set), and it is *stale* (too old to be considered usable), the client will send the value of its `ETag` along in an [`If-None-Match`](if-none-match) header field:

    If-None-Match: "33a64df551425fcc55e4d42a148795d9f25f89d4"

The server compares the client's `ETag` (sent with `If-None-Match`) with the `ETag` for its current version of the resource, and if both values match (that is, the resource has not changed), the server sends back a [`304`](../status/304) `Not Modified` status, without a body, which tells the client that the cached version of the response is still good to use (*fresh*).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7232#section-2.3">RFC 7232, section 2.3: ETag</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Conditional Requests</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`ETag`

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

`ETag`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`If-Match`](if-match)
-   [`If-None-Match`](if-none-match)
-   [`304`](../status/304)` Not Modified`
-   [`412`](../status/412)` Precondition Failed`
-   [W3C Note: Editing the Web – Detecting the Lost Update Problem Using Unreserved Checkout](https://www.w3.org/1999/04/Editing/)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/ETag$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/ETag" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/ETag</a>
