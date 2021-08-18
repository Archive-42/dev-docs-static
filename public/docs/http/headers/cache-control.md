Cache-Control
=============

The `Cache-Control` HTTP header holds *directives* (instructions) for [caching](../caching) in both requests and responses. A given directive in a request does not mean the same directive should be in the response.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/General_header">General header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/CORS-safelisted_response_header">CORS-safelisted response header</a></td><td>yes</td></tr></tbody></table>

Syntax
------

Caching directives have the following rules to be valid:

-   Case-insensitive, but lowercase is recommended.
-   Multiple directives are comma-separated.
-   Some directives have an optional argument, which can be either a *token* or a *quoted-string*. (See spec for definitions)

### Cache request directives

Standard `Cache-Control` directives that can be used by the client in an HTTP request.

    Cache-Control: max-age=<seconds>
    Cache-Control: max-stale[=<seconds>]
    Cache-Control: min-fresh=<seconds>
    Cache-Control: no-cache 
    Cache-Control: no-store
    Cache-Control: no-transform
    Cache-Control: only-if-cached

### Cache response directives

Standard `Cache-Control` directives that can be used by the server in an HTTP response.

    Cache-Control: must-revalidate
    Cache-Control: no-cache
    Cache-Control: no-store
    Cache-Control: no-transform
    Cache-Control: public
    Cache-Control: private
    Cache-Control: proxy-revalidate
    Cache-Control: max-age=<seconds>
    Cache-Control: s-maxage=<seconds>

### Extension Cache-Control directives

Extension `Cache-Control` directives are not part of the core HTTP caching standards document. Check the [compatibility table](#Browser_compatibility) for their support; user-agents that don't recognize them should ignore them.

    Cache-Control: immutable 
    Cache-Control: stale-while-revalidate=<seconds>
    Cache-Control: stale-if-error=<seconds>

Directives
----------

### Cacheability

Directives that define whether a response/request can be cached, where it may be cached, and whether it must be validated with the origin server before caching.

`public`  
The response may be stored by *any* cache, even if the response is normally non-cacheable.

`private`  
The response may be stored only by a *browser's* cache, even if the response is normally non-cacheable. `no-store` *This directive is not effective in preventing caches from storing your response.*

`no-cache`  
The response may be stored by *any* cache, even if the response is normally non-cacheable. However, the stored response MUST *always* go through validation with the origin server first before using it, therefore, you cannot use `no-cache` in-conjunction with `immutable`. `no-store` *This directive is not effective in preventing caches from storing your response.*

`no-store`  
The response may **not** be stored in *any* cache. Note that this will not prevent a valid *pre-existing* cached response being returned. Clients can set `max-age=0` to also clear existing cache responses, as this forces the cache to revalidate with the server (no other directives have an effect when used with `no-store`).

### Expiration

`max-age=<seconds>`  
The maximum amount of time a resource is considered fresh. Unlike `Expires`, this directive is relative to the time of the request.

`s-maxage=<seconds>`  
Overrides `max-age` or the `Expires` header, but only for shared caches (e.g., proxies). Ignored by private caches.

`max-stale[=<seconds>]`  
Indicates the client will accept a stale response. An optional value in seconds indicates the upper limit of staleness the client will accept.

`min-fresh=<seconds>`  
Indicates the client wants a response that will still be fresh for *at least* the specified number of seconds.

 `stale-while-revalidate=<seconds>`   
Indicates the client will accept a stale response, while asynchronously checking in the background for a fresh one. The *seconds* value indicates how long the client will accept a stale response. See "[Keeping things fresh with `stale-while-revalidate`](https://web.dev/stale-while-revalidate)" for more information.

 `stale-if-error=<seconds>`   
Indicates the client will accept a stale response if the check for a fresh one fails. The *seconds* value indicates how long the client will accept the stale response after the initial expiration.

### Revalidation and reloading

`must-revalidate`  
Indicates that once a resource becomes stale, caches must not use their stale copy without successful [validation](../caching#Cache_validation) on the origin server.

`proxy-revalidate`  
Like `must-revalidate`, but only for shared caches (e.g., proxies). Ignored by private caches.

`immutable`  
Indicates that the response body **will not change** over time. The resource, if *unexpired*, is unchanged on the server and therefore the client should not send a conditional revalidation for it (e.g. `If-None-Match` or `If-Modified-Since`) to check for updates, even when the user explicitly refreshes the page. Clients that aren't aware of this extension must ignore them as per the HTTP specification. In Firefox, `immutable` is only honored on `https://` transactions. For more information, see also this [blog post](https://bitsup.blogspot.de/2016/05/cache-control-immutable.html).

### Other

`no-transform`  
An intermediate cache or proxy cannot edit the response body, [`Content-Encoding`](content-encoding), [`Content-Range`](content-range), or [`Content-Type`](content-type). It therefore forbids a proxy or browser feature, such as [Google’s Web Light](https://support.google.com/webmasters/answer/6211428), from converting images to minimize data for a cache store or slow connection.

`only-if-cached`  
Set by the *client* to indicate "do not use the network" for the response. The cache should either respond using a stored response, or respond with a [`504`](../status/504) status code. Conditional headers such as `If-None-Match` should not be set. There is no effect if `only-if-cached` is set by a server as part of a response.

Examples
--------

### Preventing caching

To disable caching of a resource, you can send the following response header:

Good:  
    Cache-Control: no-store

The `no-store` directive will prevent a new resource being cached, but it will not prevent the cache from responding with a non-stale resource that was cached as the result of an earlier request. Setting `max-age=0` as well forces the cache to revalidate (clears the cache).

    Cache-Control: no-store, max-age=0

Bad:  
    Cache-Control: private,no-cache,no-store,max-age=0,must-revalidate,pre-check=0,post-check=0

### Caching static assets

For the files in the application that will not change, you can usually add aggressive caching by sending the response header below. This includes static files that are served by the application such as images, CSS files and JavaScript files, for example. In addition, see also the `Expires` header.

    Cache-Control: public, max-age=604800, immutable

### Requiring revalidation

Specifying `no-cache` or `max-age=0` indicates that clients can cache a resource and must revalidate each time before using it. This means HTTP request occurs each time, but it can skip downloading HTTP body if the content is valid.

    Cache-Control: no-cache
    Cache-Control: no-cache, max-age=0

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc8246">RFC 8246: HTTP Immutable Responses</a></td><td><span class="spec-RFC">IETF RFC</span></td><td></td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/rfc7234">RFC 7234: Hypertext Transfer Protocol (HTTP/1.1): Caching</a></td><td><span class="spec-RFC">IETF RFC</span></td><td></td></tr><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc5861">RFC 5861: HTTP Cache-Control Extensions for Stale Content</a></td><td><span class="spec-RFC">IETF RFC</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Cache-Control`

Yes

12

Yes

Yes

Yes

Yes

`immutable`

No

 No   
See Chromium [bug 611416](https://crbug.com/611416).

15 — 79

49

No

No

11

`stale-if-error`

No

 No   
See Chromium [bug 348877](https://crbug.com/348877).

No

 No   
See Chromium [bug 348877](https://crbug.com/348877).

No

 No   
See Bugzilla [bug 995651](https://bugzil.la/995651) comment 7.

No

No

No

`stale-while-revalidate`

75

79

68

No

No

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Cache-Control`

Yes

Yes

Yes

Yes

Yes

Yes

`immutable`

No

No

No

No

11

No

`stale-if-error`

No

No

No

No

No

No

`stale-while-revalidate`

75

75

68

No

No

No

See also
--------

-   [HTTP Caching FAQ](../caching_faq)
-   [Caching Tutorial for Web Authors and Webmasters](https://www.mnot.net/cache_docs/)
-   Guide: *[`Cache-Control` for civilians](https://csswizardry.com/2019/03/cache-control-for-civilians)*
-   [`Age`](age)
-   [`Expires`](expires)
-   [`Pragma`](pragma)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cache-Control</a>
