Origin
======

The `Origin` request header indicates where a fetch originates from. It doesn't include any path information, but only the server name. It is sent with [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) requests, as well as with [`POST`](../methods/post) requests. It is similar to the [`Referer`](referer) header, but, unlike this header, it doesn't disclose the whole path.

**Note**: The [`Origin`](origin) header is not set on [Fetch requests](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/fetch) with a method of [`HEAD`](../methods/head) or [`GET`](../methods/get) (this behavior was corrected in Firefox 65 — see [bug 1508661](https://bugzilla.mozilla.org/show_bug.cgi?id=1508661)).

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Origin: null
    Origin: <scheme> "://" <hostname> [ ":" <port> ]

Directives
----------

&lt;scheme&gt;  
The protocol that is used. Usually it is the HTTP protocol or its secured version, HTTPS.

&lt;hostname&gt;  
The domain name of the server (for virtual hosting) or the IP.

&lt;port&gt; <span class="inlineIndicator optional optionalInline">Optional</span>   
TCP port number on which the server is listening. If no port is given, the default port for the service requested (e.g., "80" for an HTTP URL) is implied.

Examples
--------

    Origin: https://developer.mozilla.org

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc6454#section-7">RFC 6454, section 7: Origin</a></td><td>The Web Origin Concept</td></tr><tr class="even"><td><a href="https://fetch.spec.whatwg.org/#origin-header">Fetch<br />
<span class="small">The definition of 'Origin header' in that specification.</span></a></td><td>Supplants the <code>Origin</code> header as defined in RFC6454.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Origin`

Yes

12

 12   
Not sent with `POST` requests, see [bug 10482384](https://developer.microsoft.com/microsoft-edge/platform/issues/10482384/).

70

70

59

Disabled

Sent with non-CORS requests since Fx59, unless they are `GET` or `HEAD`.

Disabled From version 59: this feature is behind the `network.http.sendOriginHeader` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

Partial

Not sent with `POST` requests until Firefox 58, see [bug 446344](https://bugzil.la/446344).

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

`Origin`

Yes

Yes

59

Disabled

59

Disabled

Sent with non-CORS requests since Fx59, unless they are `GET` or `HEAD`.

Disabled From version 59: this feature is behind the `network.http.sendOriginHeader` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

Partial

Not sent with `POST` requests until Firefox 58, see [bug 446344](https://bugzil.la/446344).

Yes

Yes

Yes

See also
--------

-   [`Host`](host)
-   [`Referer`](referer)
-   [Same-origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Origin$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Origin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Origin</a>
