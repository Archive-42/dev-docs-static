Connection
==========

The `Connection` general header controls whether or not the network connection stays open after the current transaction finishes. If the value sent is `keep-alive`, the connection is persistent and not closed, allowing for subsequent requests to the same server to be done.

Connection-specific header fields such as [`Connection`](connection) and [`Keep-Alive`](keep-alive) are [prohibited in HTTP/2](https://tools.ietf.org/html/rfc7540#section-8.1.2.2). Chrome and Firefox ignore them in HTTP/2 responses, but Safari conforms to the HTTP/2 spec requirements and won’t load any response which contains them.

Except for the standard hop-by-hop headers ([`Keep-Alive`](keep-alive), [`Transfer-Encoding`](transfer-encoding), [`TE`](te), [`Connection`](connection), [`Trailer`](trailer), [`Upgrade`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Upgrade), [`Proxy-Authorization`](proxy-authorization) and [`Proxy-Authenticate`](proxy-authenticate)), any hop-by-hop headers used by the message must be listed in the `Connection` header, so that the first proxy knows it has to consume them and not forward them further. Standard hop-by-hop headers can be listed too (it is often the case of [`Keep-Alive`](keep-alive), but this is not mandatory).

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/General_header">General header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Connection: keep-alive
    Connection: close

Directives
----------

`close`  
Indicates that either the client or the server would like to close the connection. This is the default on HTTP/1.0 requests.

any comma-separated list of HTTP headers \[Usually `keep-alive` only\]  
Indicates that the client would like to keep the connection open. Having a persistent connection is the default on HTTP/1.1 requests. The list of headers are the name of the header to be removed by the first non-transparent proxy or cache in-between: these headers define the connection between the emitter and the first entity, not the destination node.

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Connection`

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

`Connection`

Yes

Yes

Yes

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Connection$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Connection" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Connection</a>
