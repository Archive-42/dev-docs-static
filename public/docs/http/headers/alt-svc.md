Alt-Svc
=======

The `Alt-Svc` HTTP response header is used to advertise alternative services through which the same resource can be reached. An alternative service is defined by a protocol/host/port combination.

Syntax
------

    Alt-Svc: clear
    Alt-Svc: <protocol-id>=<alt-authority>; ma=<max-age>
    Alt-Svc: <protocol-id>=<alt-authority>; ma=<max-age>; persist=1

`clear`  
The special value ''clear" indicates that the origin requests all alternatives for that origin to be invalidated.

`<protocol-id>`  
The [ALPN](https://developer.mozilla.org/en-US/docs/Glossary/ALPN) protocol identifier. Examples include h2 for HTTP/2 and h3-25 for draft 25 of the HTTP/3 protocol.

`<alt-authority>`  
The quoted string specifying the alternative authority which consists of an optional host override, a colon, and a mandatory port number.

 `ma=<max-age>`<span class="inlineIndicator optional optionalInline">Optional</span>   
The number of seconds for which the alternative service is considered fresh. If omitted, it defaults to 24 hours. Alternative service entries can be cached for up to *&lt;max-age&gt;* seconds, minus the age of the response (from the [`Age`](age) header). If the cached entry expires, the client can no longer use this alternative service for new connections.

 `persist=1`<span class="inlineIndicator optional optionalInline">Optional</span>   
Usually cached alternative service entries are cleared on network configuration changes. Use of the persist=1 parameter ensures that the entry is not deleted through such changes.

Multiple entries can be specified in a single `Alt-Svc` header using comma as separator. In that case, early entries are considered more preferable.

Example
-------

    Alt-Svc: h2=":443"; ma=2592000;
    Alt-Svc: h2=":443"; ma=2592000; persist=1
    Alt-Svc: h2="alt.example.com:443", h2=":443"
    Alt-Svc: h3-25=":443"; ma=3600, h2=":443"; ma=3600

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7838">RFC 7838</a></td><td><span class="spec-RFC">IETF RFC</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Alt-Svc`

Yes

≤79

38

38

37 — 38

Only supports draft-04

35 — 37

Disabled

Only supports draft-03

Disabled From version 35 until version 37 (exclusive): this feature is behind the `network.http.altsvc.enabled` preference (needs to be set to `true`) and the `altsvc.oe` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

?

Yes

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Alt-Svc`

Yes

Yes

38

38

37 — 38

Only supports draft-04

35 — 37

Disabled

Only supports draft-03

Disabled From version 35 until version 37 (exclusive): this feature is behind the `network.http.altsvc.enabled` preference (needs to be set to `true`) and the `altsvc.oe` preference (needs to be set to `true`). To change preferences in Firefox, visit about:config.

Yes

?

Yes

See also
--------

-   [Identifying resources on the Web](../basics_of_http/identifying_resources_on_the_web)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Alt-Svc$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Alt-Svc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Alt-Svc</a>
