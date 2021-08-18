Headers
=======

**HTTP headers** let the client and the server pass additional information with an HTTP request or response. An HTTP header consists of its case-insensitive name followed by a colon (`:`), then by its value. [Whitespace](https://developer.mozilla.org/en-US/docs/Glossary/Whitespace) before the value is ignored.

Custom proprietary headers have historically been used with an `X-` prefix, but this convention was deprecated in June 2012 because of the inconveniences it caused when nonstandard fields became standard in [RFC 6648](https://tools.ietf.org/html/rfc6648); others are listed in an [IANA registry](http://www.iana.org/assignments/message-headers/perm-headers.html), whose original content was defined in [RFC 4229](http://tools.ietf.org/html/rfc4229). IANA also maintains a [registry of proposed new HTTP headers](http://www.iana.org/assignments/message-headers/prov-headers.html).

Headers can be grouped according to their contexts:

-   [General headers](https://developer.mozilla.org/en-US/docs/Glossary/General_header) apply to both requests and responses, but with no relation to the data transmitted in the body.
-   [Request headers](https://developer.mozilla.org/en-US/docs/Glossary/Request_header) contain more information about the resource to be fetched, or about the client requesting the resource.
-   [Response headers](https://developer.mozilla.org/en-US/docs/Glossary/Response_header) hold additional information about the response, like its location or about the server providing it.
-   [Entity headers](https://developer.mozilla.org/en-US/docs/Glossary/Entity_header) contain information about the body of the resource, like its [content length](headers/content-length) or [MIME type](basics_of_http/mime_types).

Headers can also be grouped according to how [proxies](https://developer.mozilla.org/en-US/docs/Glossary/Proxy_server) handle them:

-   [`Connection`](headers/connection)
-   [`Keep-Alive`](headers/keep-alive)
-   [`Proxy-Authenticate`](headers/proxy-authenticate)
-   [`Proxy-Authorization`](headers/proxy-authorization)
-   [`TE`](headers/te)
-   [`Trailer`](headers/trailer)
-   [`Transfer-Encoding`](headers/transfer-encoding)
-   [`Upgrade`](headers/upgrade) (see also [Protocol upgrade mechanism](protocol_upgrade_mechanism)).

End-to-end headers  
These headers *must* be transmitted to the final recipient of the message: the server for a request, or the client for a response. Intermediate proxies must retransmit these headers unmodified and caches must store them.

Hop-by-hop headers  
These headers are meaningful only for a single transport-level connection, and *must not* be retransmitted by proxies or cached. Note that only hop-by-hop headers may be set using the [`Connection`](headers/connection) general header.

Authentication
--------------

[`WWW-Authenticate`](headers/www-authenticate)  
Defines the authentication method that should be used to access a resource.

[`Authorization`](headers/authorization)  
Contains the credentials to authenticate a user-agent with a server.

[`Proxy-Authenticate`](headers/proxy-authenticate)  
Defines the authentication method that should be used to access a resource behind a proxy server.

[`Proxy-Authorization`](headers/proxy-authorization)  
Contains the credentials to authenticate a user agent with a proxy server.

Caching
-------

[`Age`](headers/age)  
The time, in seconds, that the object has been in a proxy cache.

[`Cache-Control`](headers/cache-control)  
Directives for caching mechanisms in both requests and responses.

[`Clear-Site-Data`](headers/clear-site-data)  
Clears browsing data (e.g. cookies, storage, cache) associated with the requesting website.

[`Expires`](headers/expires)  
The date/time after which the response is considered stale.

[`Pragma`](headers/pragma)  
Implementation-specific header that may have various effects anywhere along the request-response chain. Used for backwards compatibility with HTTP/1.0 caches where the `Cache-Control` header is not yet present.

[`Warning`](headers/warning)  
General warning information about possible problems.

Client hints
------------

HTTP [Client hints](https://developer.mozilla.org/en-US/docs/Glossary/Client_hints) are a work in progress. Actual documentation can be found on the [website of the HTTP working group](https://httpwg.org/http-extensions/client-hints.html).

 [`Accept-CH`](headers/accept-ch)   
Servers can advertise support for Client Hints using the `Accept-CH` header field or an equivalent HTML `<meta>` element with `http-equiv` attribute ([\[HTML5\]](https://httpwg.org/http-extensions/client-hints.html#HTML5)).

 [`Accept-CH-Lifetime`](headers/accept-ch-lifetime)   
Servers can ask the client to remember the set of Client Hints that the server supports for a specified period of time, to enable delivery of Client Hints on subsequent requests to the server’s origin ([\[RFC6454\]](https://httpwg.org/http-extensions/client-hints.html#RFC6454)).

 [`Early-Data`](headers/early-data)   
Indicates that the request has been conveyed in early data.

 [`Content-DPR`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-DPR)   
A number that indicates the ratio between physical pixels over CSS pixels of the selected image response.

 [`DPR`](headers/dpr)   
A number that indicates the client’s current Device Pixel Ratio (DPR), which is the ratio of physical pixels over CSS pixels (Section 5.2 of [\[CSSVAL\]](https://httpwg.org/http-extensions/client-hints.html#CSSVAL)) of the layout viewport (Section 9.1.1 of [\[CSS2\]](https://httpwg.org/http-extensions/client-hints.html#CSS2)) on the device.

 [`Device-Memory`](headers/device-memory)   
Technically a part of Device Memory API, this header represents an approximate amount of RAM client has.

 [`Save-Data`](headers/save-data)   
A boolean that indicates the user agent's preference for reduced data usage.

 [`Viewport-Width`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Viewport-Width)   
A number that indicates the layout viewport width in CSS pixels. The provided pixel value is a number rounded to the smallest following integer (i.e. ceiling value).

If `Viewport-Width` occurs in a message more than once, the last value overrides all previous occurrences.

 [`Width`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Width)   
The `Width` request header field is a number that indicates the desired resource width in physical pixels (i.e. intrinsic size of an image). The provided pixel value is a number rounded to the smallest following integer (i.e. ceiling value).

If the desired resource width is not known at the time of the request or the resource does not have a display width, the `Width` header field can be omitted. If `Width` occurs in a message more than once, the last value overrides all previous occurrences

Conditionals
------------

[`Last-Modified`](headers/last-modified)  
The last modification date of the resource, used to compare several versions of the same resource. It is less accurate than [`ETag`](headers/etag), but easier to calculate in some environments. Conditional requests using [`If-Modified-Since`](headers/if-modified-since) and [`If-Unmodified-Since`](headers/if-unmodified-since) use this value to change the behavior of the request.

[`ETag`](headers/etag)  
A unique string identifying the version of the resource. Conditional requests using [`If-Match`](headers/if-match) and [`If-None-Match`](headers/if-none-match) use this value to change the behavior of the request.

[`If-Match`](headers/if-match)  
Makes the request conditional, and applies the method only if the stored resource matches one of the given ETags.

[`If-None-Match`](headers/if-none-match)  
Makes the request conditional, and applies the method only if the stored resource *doesn't* match any of the given ETags. This is used to update caches (for safe requests), or to prevent to upload a new resource when one already exists.

[`If-Modified-Since`](headers/if-modified-since)  
Makes the request conditional, and expects the entity to be transmitted only if it has been modified after the given date. This is used to transmit data only when the cache is out of date.

[`If-Unmodified-Since`](headers/if-unmodified-since)  
Makes the request conditional, and expects the entity to be transmitted only if it has not been modified after the given date. This ensures the coherence of a new fragment of a specific range with previous ones, or to implement an optimistic concurrency control system when modifying existing documents.

[`Vary`](headers/vary)  
Determines how to match request headers to decide whether a cached response can be used rather than requesting a fresh one from the origin server.

Connection management
---------------------

[`Connection`](headers/connection)  
Controls whether the network connection stays open after the current transaction finishes.

[`Keep-Alive`](headers/keep-alive)  
Controls how long a persistent connection should stay open.

[Content negotiation](content_negotiation)
------------------------------------------

[`Accept`](headers/accept)  
Informs the server about the [types](https://developer.mozilla.org/en-US/docs/Glossary/MIME_type) of data that can be sent back.

[`Accept-Charset`](headers/accept-charset)  
Which [character encodings](https://developer.mozilla.org/en-US/docs/Glossary/character_encodings) the client understands.

[`Accept-Encoding`](headers/accept-encoding)  
The encoding algorithm, usually a [compression algorithm](compression), that can be used on the resource sent back.

[`Accept-Language`](headers/accept-language)  
Informs the server about the human language the server is expected to send back. This is a hint and is not necessarily under the full control of the user: the server should always pay attention not to override an explicit user choice (like selecting a language from a dropdown).

Controls
--------

[`Expect`](headers/expect)

Indicates expectations that need to be fulfilled by the server to properly handle the request.

[`Max-Forwards`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Max-Forwards)

Cookies
-------

[`Cookie`](headers/cookie)  
Contains stored [HTTP cookies](cookies) previously sent by the server with the [`Set-Cookie`](headers/set-cookie) header.

[`Set-Cookie`](headers/set-cookie)  
Send cookies from the server to the user-agent.

 [`Cookie2`](headers/cookie2)   
Contains an HTTP cookie previously sent by the server with the [`Set-Cookie2`](headers/set-cookie2) header, but has been **obsoleted**. Use [`Cookie`](headers/cookie) instead.

 [`Set-Cookie2`](headers/set-cookie2)   
Sends cookies from the server to the user-agent, but has been **obsoleted**. Use [`Set-Cookie`](headers/set-cookie) instead.

CORS
----

*Learn more about CORS [here](cors).*

[`Access-Control-Allow-Origin`](headers/access-control-allow-origin)  
Indicates whether the response can be shared.

[`Access-Control-Allow-Credentials`](headers/access-control-allow-credentials)  
Indicates whether the response to the request can be exposed when the credentials flag is true.

[`Access-Control-Allow-Headers`](headers/access-control-allow-headers)  
Used in response to a [preflight request](https://developer.mozilla.org/en-US/docs/Glossary/Preflight_request) to indicate which HTTP headers can be used when making the actual request.

[`Access-Control-Allow-Methods`](headers/access-control-allow-methods)  
Specifies the methods allowed when accessing the resource in response to a preflight request.

[`Access-Control-Expose-Headers`](headers/access-control-expose-headers)  
Indicates which headers can be exposed as part of the response by listing their names.

[`Access-Control-Max-Age`](headers/access-control-max-age)  
Indicates how long the results of a preflight request can be cached.

[`Access-Control-Request-Headers`](headers/access-control-request-headers)  
Used when issuing a preflight request to let the server know which HTTP headers will be used when the actual request is made.

[`Access-Control-Request-Method`](headers/access-control-request-method)  
Used when issuing a preflight request to let the server know which [HTTP method](methods) will be used when the actual request is made.

[`Origin`](headers/origin)  
Indicates where a fetch originates from.

[`Timing-Allow-Origin`](headers/timing-allow-origin)  
Specifies origins that are allowed to see values of attributes retrieved via features of the [Resource Timing API](https://developer.mozilla.org/en-US/docs/Web/API/Resource_Timing_API), which would otherwise be reported as zero due to cross-origin restrictions.

Do Not Track
------------

[`DNT`](headers/dnt)  
Expresses the user's tracking preference.

[`Tk`](headers/tk)  
Indicates the tracking status of the corresponding response.

Downloads
---------

[`Content-Disposition`](headers/content-disposition)  
Indicates if the resource transmitted should be displayed inline (default behavior without the header), or if it should be handled like a download and the browser should present a “Save As” dialog.

Message body information
------------------------

[`Content-Length`](headers/content-length)  
The size of the resource, in decimal number of bytes.

[`Content-Type`](headers/content-type)  
Indicates the media type of the resource.

[`Content-Encoding`](headers/content-encoding)  
Used to specify the compression algorithm.

[`Content-Language`](headers/content-language)  
Describes the human language(s) intended for the audience, so that it allows a user to differentiate according to the users' own preferred language.

[`Content-Location`](headers/content-location)  
Indicates an alternate location for the returned data.

Proxies
-------

[`Forwarded`](headers/forwarded)  
Contains information from the client-facing side of proxy servers that is altered or lost when a proxy is involved in the path of the request.

 [`X-Forwarded-For`](headers/x-forwarded-for)   
Identifies the originating IP addresses of a client connecting to a web server through an HTTP proxy or a load balancer.

 [`X-Forwarded-Host`](headers/x-forwarded-host)   
Identifies the original host requested that a client used to connect to your proxy or load balancer.

 [`X-Forwarded-Proto`](headers/x-forwarded-proto)   
Identifies the protocol (HTTP or HTTPS) that a client used to connect to your proxy or load balancer.

[`Via`](headers/via)  
Added by proxies, both forward and reverse proxies, and can appear in the request headers and the response headers.

Redirects
---------

[`Location`](headers/location)  
Indicates the URL to redirect a page to.

Request context
---------------

[`From`](headers/from)  
Contains an Internet email address for a human user who controls the requesting user agent.

[`Host`](headers/host)  
Specifies the domain name of the server (for virtual hosting), and (optionally) the TCP port number on which the server is listening.

[`Referer`](headers/referer)  
The address of the previous web page from which a link to the currently requested page was followed.

[`Referrer-Policy`](headers/referrer-policy)  
Governs which referrer information sent in the [`Referer`](headers/referer) header should be included with requests made.

[`User-Agent`](headers/user-agent)  
Contains a characteristic string that allows the network protocol peers to identify the application type, operating system, software vendor or software version of the requesting software user agent. See also the [Firefox user agent string reference](headers/user-agent/firefox).

Response context
----------------

[`Allow`](headers/allow)  
Lists the set of HTTP request methods supported by a resource.

[`Server`](headers/server)  
Contains information about the software used by the origin server to handle the request.

Range requests
--------------

[`Accept-Ranges`](headers/accept-ranges)  
Indicates if the server supports range requests, and if so in which unit the range can be expressed.

[`Range`](headers/range)  
Indicates the part of a document that the server should return.

[`If-Range`](headers/if-range)  
Creates a conditional range request that is only fulfilled if the given etag or date matches the remote resource. Used to prevent downloading two ranges from incompatible version of the resource.

[`Content-Range`](headers/content-range)  
Indicates where in a full body message a partial message belongs.

Security
--------

 [`Cross-Origin-Embedder-Policy`](headers/cross-origin-embedder-policy) ([COEP](https://developer.mozilla.org/en-US/docs/Glossary/COEP))  
Allows a server to declare an embedder policy for a given document.

<!-- -->

 [`Cross-Origin-Opener-Policy`](headers/cross-origin-opener-policy) ([COOP](https://developer.mozilla.org/en-US/docs/Glossary/COOP))  
Prevents other domains from opening/controlling a window.

<!-- -->

 [`Cross-Origin-Resource-Policy`](headers/cross-origin-resource-policy) ([CORP](https://developer.mozilla.org/en-US/docs/Glossary/CORP))  
Prevents other domains from reading the response of the resources to which this header is applied.

 [`Content-Security-Policy`](headers/content-security-policy) ([CSP](https://developer.mozilla.org/en-US/docs/Glossary/CSP))  
Controls resources the user agent is allowed to load for a given page.

[`Content-Security-Policy-Report-Only`](headers/content-security-policy-report-only)  
Allows web developers to experiment with policies by monitoring, but not enforcing, their effects. These violation reports consist of [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON) documents sent via an HTTP `POST` request to the specified URI.

[`Expect-CT`](headers/expect-ct)  
Allows sites to opt in to reporting and/or enforcement of Certificate Transparency requirements, which prevents the use of misissued certificates for that site from going unnoticed. When a site enables the Expect-CT header, they are requesting that Chrome check that any certificate for that site appears in public CT logs.

[`Feature-Policy`](headers/feature-policy)  
Provides a mechanism to allow and deny the use of browser features in its own frame, and in iframes that it embeds.

<!-- -->

 [`Origin-Isolation`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Origin-Isolation)   
Provides a mechanism to allow web applications to isolate their origins.

<!-- -->

 [`Strict-Transport-Security`](headers/strict-transport-security) ([HSTS](https://developer.mozilla.org/en-US/docs/Glossary/HSTS))  
Force communication using HTTPS instead of HTTP.

[`Upgrade-Insecure-Requests`](headers/upgrade-insecure-requests)  
Sends a signal to the server expressing the client’s preference for an encrypted and authenticated response, and that it can successfully handle the [`upgrade-insecure-requests`](headers/content-security-policy/upgrade-insecure-requests) directive.

[`X-Content-Type-Options`](headers/x-content-type-options)  
Disables MIME sniffing and forces browser to use the type given in [`Content-Type`](headers/content-type).

[`X-Download-Options`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Download-Options)  
The `X-Download-Options` HTTP header indicates that the browser (Internet Explorer) should not display the option to "Open" a file that has been downloaded from an application, to prevent phishing attacks as the file otherwise would gain access to execute in the context of the application. (Note: related [MS Edge bug](https://developer.microsoft.com/en-us/microsoft-edge/platform/issues/18488178/)).

 [`X-Frame-Options`](headers/x-frame-options) (XFO)  
Indicates whether a browser should be allowed to render a page in a [`<frame>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame), [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe), [`<embed>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/embed) or [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object).

[`X-Permitted-Cross-Domain-Policies`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Permitted-Cross-Domain-Policies)  
Specifies if a cross-domain policy file (`crossdomain.xml`) is allowed. The file may define a policy to grant clients, such as Adobe's Flash Player (now obsolete), Adobe Acrobat, Microsoft Silverlight (now obsolete), or Apache Flex, permission to handle data across domains that would otherwise be restricted due to the [Same-Origin Policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy). See the [Cross-domain Policy File Specification](https://www.adobe.com/devnet/articles/crossdomain_policy_file_spec.html) for more information.

[`X-Powered-By`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Powered-By)  
May be set by hosting environments or other frameworks and contains information about them while not providing any usefulness to the application or its visitors. Unset this header to avoid exposing potential vulnerabilities.

[`X-XSS-Protection`](headers/x-xss-protection)  
Enables cross-site scripting filtering.

### HTTP Public Key Pinning ([HPKP](https://developer.mozilla.org/en-US/docs/Glossary/HPKP))

HTTP Public Key Pinning has been deprecated and removed in favor of Certificate Transparency and [`Expect-CT`](headers/expect-ct).

[`Public-Key-Pins`](headers/public-key-pins)  
Associates a specific cryptographic public key with a certain web server to decrease the risk of [MITM](https://developer.mozilla.org/en-US/docs/Glossary/MITM) attacks with forged certificates.

[`Public-Key-Pins-Report-Only`](headers/public-key-pins-report-only)  
Sends reports to the report-uri specified in the header and does still allow clients to connect to the server even if the pinning is violated.

### Fetch metadata request headers

[`Sec-Fetch-Site`](headers/sec-fetch-site)  
It is a request header that indicates the relationship between a request initiator's origin and its target's origin. It is a Structured Header whose value is a token with possible values `cross-site`, `same-origin`, `same-site`, and `none`.

[`Sec-Fetch-Mode`](headers/sec-fetch-mode)  
It is a request header that indicates the request's mode to a server. It is a Structured Header whose value is a token with possible values `cors`, `navigate`, `nested-navigate`, `no-cors`, `same-origin`, and `websocket`.

[`Sec-Fetch-User`](headers/sec-fetch-user)  
It is a request header that indicates whether or not a navigation request was triggered by user activation. It is a Structured Header whose value is a boolean so possible values are `?0` for false and `?1` for true.

[`Sec-Fetch-Dest`](headers/sec-fetch-dest)  
It is a request header that indicates the request's destination to a server. It is a Structured Header whose value is a token with possible values `audio`, `audioworklet`, `document`, `embed`, `empty`, `font`, `image`, `manifest`, `object`, `paintworklet`, `report`, `script`, `serviceworker`, `sharedworker`, `style`, `track`, `video`, `worker`, `xslt`, and `nested-document`.

Server-sent events
------------------

[`Last-Event-ID`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Last-Event-ID)  
...

 [`NEL`](headers/nel)   
Defines a mechanism that enables developers to declare a network error reporting policy.

[`Ping-From`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Ping-From)  
...

[`Ping-To`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Ping-To)  
...

[`Report-To`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Report-To)  
Used to specify a server endpoint for the browser to send warning and error reports to.

Transfer coding
---------------

[`Transfer-Encoding`](headers/transfer-encoding)  
Specifies the form of encoding used to safely transfer the entity to the user.

[`TE`](headers/te)  
Specifies the transfer encodings the user agent is willing to accept.

[`Trailer`](headers/trailer)  
Allows the sender to include additional fields at the end of chunked message.

WebSockets
----------

[`Sec-WebSocket-Key`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-WebSocket-Key)  
...

[`Sec-WebSocket-Extensions`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-WebSocket-Extensions)  
...

[`Sec-WebSocket-Accept`](headers/sec-websocket-accept)  
...

[`Sec-WebSocket-Protocol`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-WebSocket-Protocol)  
...

[`Sec-WebSocket-Version`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-WebSocket-Version)  
...

Other
-----

 [`Accept-Push-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Push-Policy)   
A client can express the desired push policy for a request by sending an `Accept-Push-Policy` header field in the request.

 [`Accept-Signature`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Signature)   
A client can send the `Accept-Signature` header field to indicate intention to take advantage of any available signatures and to indicate what kinds of signatures it supports.

[`Alt-Svc`](headers/alt-svc)  
Used to list alternate ways to reach this service.

[`Date`](headers/date)  
Contains the date and time at which the message was originated.

[`Large-Allocation`](headers/large-allocation)  
Tells the browser that the page being loaded is going to want to perform a large allocation.

[`Link`](headers/link)  
The `Link` entity-header field provides a means for serialising one or more links in HTTP headers. It is semantically equivalent to the HTML [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) element.

 [`Push-Policy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Push-Policy)   
A `Push-Policy` defines the server behaviour regarding push when processing a request.

[`Retry-After`](headers/retry-after)  
Indicates how long the user agent should wait before making a follow-up request.

 [`Signature`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Signature)   
The `Signature` header field conveys a list of signatures for an exchange, each one accompanied by information about how to determine the authority of and refresh that signature.

 [`Signed-Headers`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Signed-Headers)   
The `Signed-Headers` header field identifies an ordered list of response header fields to include in a signature.

[`Server-Timing`](headers/server-timing)  
Communicates one or more metrics and descriptions for the given request-response cycle.

[`Service-Worker-Allowed`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Service-Worker-Allowed)  
Used to remove the [path restriction](https://w3c.github.io/ServiceWorker/#path-restriction) by including this header [in the response of the Service Worker script](https://w3c.github.io/ServiceWorker/#service-worker-script-response).

[`SourceMap`](headers/sourcemap)  
Links generated code to a [source map](https://developer.mozilla.org/en-US/docs/Tools/Debugger/How_to/Use_a_source_map).

[`Upgrade`](headers/upgrade)  
The relevant RFC document for the [Upgrade header field is RFC 7230, section 6.7](https://tools.ietf.org/html/rfc7230#section-6.7). The standard establishes rules for upgrading or changing to a different protocol on the current client, server, transport protocol connection. For example, this header standard allows a client to change from HTTP 1.1 to HTTP 2.0, assuming the server decides to acknowledge and implement the Upgrade header field. Neither party is required to accept the terms specified in the Upgrade header field. It can be used in both client and server headers. If the Upgrade header field is specified, then the sender MUST also send the Connection header field with the upgrade option specified. For details on the Connection header field [please see section 6.1 of the aforementioned RFC](https://tools.ietf.org/html/rfc7230#section-6.1).

[`X-DNS-Prefetch-Control`](headers/x-dns-prefetch-control)  
Controls DNS prefetching, a feature by which browsers proactively perform domain name resolution on both links that the user may choose to follow as well as URLs for items referenced by the document, including images, CSS, JavaScript, and so forth.

 [`X-Firefox-Spdy`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Firefox-Spdy)   
...

 [`X-Pingback`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Pingback)   
...

[`X-Requested-With`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Requested-With)  
...

 [`X-Robots-Tag`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Robots-Tag)   
The `X-Robots-Tag` HTTP header is used to indicate how a web page is to be indexed within public search engine results. The header is effectively equivalent to `<meta name="robots" content="...">`.

 [`X-UA-Compatible`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-UA-Compatible)   
Used by Internet Explorer to signal which document mode to use.

Contributing
------------

You can help by [writing new entries](https://developer.mozilla.org/en-US/docs/MDN/Contribute/Howto/Document_an_HTTP_header) or improving the existing ones.

See also
--------

-   [Wikipedia page on List of HTTP headers](https://en.wikipedia.org/wiki/List_of_HTTP_header_fields)
-   [IANA registry](https://www.iana.org/assignments/message-headers/perm-headers.html)
-   [HTTP Working Group](https://httpwg.org/specs/)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers</a>
