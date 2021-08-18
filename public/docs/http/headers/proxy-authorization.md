Proxy-Authorization
===================

The HTTP `Proxy-Authorization` request header contains the credentials to authenticate a user agent to a proxy server, usually after the server has responded with a [`407`](../status/407) `Proxy Authentication Required` status and the [`Proxy-Authenticate`](proxy-authenticate) header.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Proxy-Authorization: <type> <credentials>

Directives
----------

&lt;type&gt;  
[Authentication type](../authentication#Authentication_schemes). A common type is ["Basic"](../authentication#Basic_authentication_scheme). See also the [IANA registry of Authentication schemes](http://www.iana.org/assignments/http-authschemes/http-authschemes.xhtml).

&lt;credentials&gt;  
The credentials are constructed like this:

-   The username and the password are combined with a colon (`aladdin:opensesame`).
-   The resulting string is [base64](https://developer.mozilla.org/en-US/docs/Web/API/WindowBase64/Base64_encoding_and_decoding) encoded (`YWxhZGRpbjpvcGVuc2VzYW1l`).

**Note**: Base64 encoding does not mean encryption or hashing! This method is equally secure as sending the credentials in clear text (base64 is a reversible encoding). Prefer to use HTTPS in conjunction with Basic Authentication.

Examples
--------

    Proxy-Authorization: Basic YWxhZGRpbjpvcGVuc2VzYW1l

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7235#section-4.4">RFC 7235, section 4.4: Proxy-Authorization</a></td><td>HTTP/1.1: Authentication</td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/rfc7617">RFC 7617</a></td><td>The 'Basic' HTTP Authentication Scheme</td></tr></tbody></table>

See also
--------

-   [HTTP authentication](../authentication)
-   [`Proxy-Authenticate`](proxy-authenticate)
-   [`WWW-Authenticate`](www-authenticate)
-   [`Authorization`](authorization)
-   [`401`](../status/401), [`403`](../status/403), [`407`](../status/407)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Proxy-Authorization$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Proxy-Authorization" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Proxy-Authorization</a>
