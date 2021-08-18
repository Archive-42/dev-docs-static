Cookie
======

The `Cookie` HTTP request header contains stored [HTTP cookies](../cookies) previously sent by the server with the [`Set-Cookie`](set-cookie) header.

The `Cookie` header is optional and may be omitted if, for example, the browser's privacy settings block cookies.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>yes</td></tr></tbody></table>

Syntax
------

    Cookie: <cookie-list>
    Cookie: name=value
    Cookie: name=value; name2=value2; name3=value3

&lt;cookie-list&gt;  
A list of name-value pairs in the form of `<cookie-name>=<cookie-value>`. Pairs in the list are separated by a semicolon and a space (`'; '`).

Examples
--------

    Cookie: PHPSESSID=298zf09hf012fh2; csrftoken=u32t4o3tb3gg43; _gat=1

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc6265#section-5.4">RFC 6265, section 5.4: Cookie</a></td><td>HTTP State Management Mechanism</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Cookie`

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

`Cookie`

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`Set-Cookie`](set-cookie)
-   [`Document.cookie`](https://developer.mozilla.org/en-US/docs/Web/API/Document/cookie)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cookie$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cookie" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Cookie</a>
