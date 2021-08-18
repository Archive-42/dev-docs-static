Server
======

The `Server` header describes the software used by the origin server that handled the request — that is, the server that generated the response.

Avoid overly-detailed `Server` values, as they can reveal information that might make it (slightly) easier for attackers to exploit known security holes.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Server: <product>

Directives
----------

`<product>`  
The name of the software or product that handled the request. Usually in a format similar to [`User-Agent`](user-agent).

How much detail to include is an interesting balance to strike; exposing the OS version is probably a bad idea, as mentioned in the earlier warning about overly-detailed values. However, exposed Apache versions helped browsers work around a bug those versions had with [`Content-Encoding`](content-encoding) combined with [`Range`](range).

Examples
--------

    Server: Apache/2.4.1 (Unix)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-7.4.2">RFC 7231, section 7.4.2: Server</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Server`

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

`Server`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Allow`](allow)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Server$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Server" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Server</a>
