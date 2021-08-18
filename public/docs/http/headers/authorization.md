Authorization
=============

The HTTP `Authorization` request header contains the credentials to authenticate a user agent with a server, usually, but not necessarily, after the server has responded with a [`401`](../status/401) `Unauthorized` status and the [`WWW-Authenticate`](www-authenticate) header.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Request_header">Request header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Authorization: <type> <credentials>

Directives
----------

&lt;type&gt;  
[Authentication type](../authentication#Authentication_schemes). A common type is ["Basic"](../authentication#Basic_authentication_scheme). Other types:

-   [IANA registry of Authentication schemes](http://www.iana.org/assignments/http-authschemes/http-authschemes.xhtml)
-   [Authentification for AWS servers (`AWS4-HMAC-SHA256`)](http://docs.aws.amazon.com/AmazonS3/latest/API/sigv4-auth-using-authorization-header.html)

&lt;credentials&gt;  
If the "Basic" authentication scheme is used, the credentials are constructed like this:

-   The username and the password are combined with a colon (`aladdin:opensesame`).
-   The resulting string is [base64](https://developer.mozilla.org/en-US/docs/Web/API/WindowBase64/Base64_encoding_and_decoding) encoded (`YWxhZGRpbjpvcGVuc2VzYW1l`).

**Note**: Base64 encoding does not mean encryption or hashing! This method is equally secure as sending the credentials in clear text (base64 is a reversible encoding). Prefer to use HTTPS in conjunction with Basic Authentication.

Examples
--------

    Authorization: Basic YWxhZGRpbjpvcGVuc2VzYW1l

See also [HTTP authentication](../authentication) for examples on how to configure Apache or nginx servers to password protect your site with HTTP basic authentication.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7235#section-4.2">RFC 7235, section 4.2: Authorization</a></td><td>HTTP/1.1: Authentication</td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/rfc7617">RFC 7617</a></td><td>The 'Basic' HTTP Authentication Scheme</td></tr></tbody></table>

See also
--------

-   [HTTP authentication](../authentication)
-   [`WWW-Authenticate`](www-authenticate)
-   [`Proxy-Authorization`](proxy-authorization)
-   [`Proxy-Authenticate`](proxy-authenticate)
-   [`401`](../status/401), [`403`](../status/403), [`407`](../status/407)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Authorization</a>
