Forwarded
=========

The `Forwarded` header contains information from the [reverse proxy servers](../proxy_servers_and_tunneling) that is altered or lost when a proxy is involved in the path of the request.

The alternative and de-facto standard versions of this header are the [`X-Forwarded-For`](x-forwarded-for), [`X-Forwarded-Host`](x-forwarded-host) and [`X-Forwarded-Proto`](x-forwarded-proto) headers.

This header is used for debugging, statistics, and generating location-dependent content and by design it exposes privacy sensitive information, such as the IP address of the client. Therefore the user's privacy must be kept in mind when deploying this header.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Forwarded: by=<identifier>;for=<identifier>;host=<host>;proto=<http|https>

Directives
----------

&lt;identifier&gt;  
An identifier disclosing the information that is altered or lost when using a proxy. This can be either:

-   an IP address (v4 or v6, optionally with a port, and ipv6 quoted and enclosed in square brackets),
-   an obfuscated identifier (such as "\_hidden" or "\_secret"),
-   or "unknown" when the preceding entity is not known (and you still want to indicate that forwarding of the request was made).

by=&lt;identifier&gt;  
The interface where the request came in to the proxy server.

for=&lt;identifier&gt;  
The client that initiated the request and subsequent proxies in a chain of proxies.

host=&lt;host&gt;  
The [`Host`](host) request header field as received by the proxy.

proto=&lt;http|https&gt;  
Indicates which protocol was used to make the request (typically "http" or "https").

Examples
--------

### Using the `Forwarded` header

    Forwarded: for="_mdn" 

    # case insensitive
    Forwarded: For="[2001:db8:cafe::17]:4711"

    # separated by semicolon
    Forwarded: for=192.0.2.60;proto=http;by=203.0.113.43

    # multiple values can be appended using a comma
    Forwarded: for=192.0.2.43, for=198.51.100.17

### Transitioning from `X-Forwarded-For` to `Forwarded`

If your application, server, or proxy supports the standardized `Forwarded` header, the [`X-Forwarded-For`](x-forwarded-for) header can be replaced. Note that IPv6 address are quoted and enclosed in square brackets in `Forwarded`.

    X-Forwarded-For: 123.34.567.89
    Forwarded: for=123.34.567.89

    X-Forwarded-For: 192.0.2.43, "[2001:db8:cafe::17]"
    Forwarded: for=192.0.2.43, for="[2001:db8:cafe::17]"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7239#section-4">RFC 7239, section 4: Forwarded</a></td><td>Forwarded HTTP Extension</td></tr></tbody></table>

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Forwarded`

?

?

?

?

?

?

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Forwarded`

?

?

?

?

?

?

See also
--------

-   [`X-Forwarded-For`](x-forwarded-for)
-   [`X-Forwarded-Host`](x-forwarded-host)
-   [`X-Forwarded-Proto`](x-forwarded-proto)
-   [`Via`](via) – provides information about the proxy itself, not about the client connecting to it.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Forwarded$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Forwarded" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Forwarded</a>
