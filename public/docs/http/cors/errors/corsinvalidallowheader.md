Errors: CORSInvalidAllowHeader
==============================

Reason
------

    Reason: invalid token ‘xyz’ in CORS header ‘Access-Control-Allow-Headers’

What went wrong?
----------------

The response to the [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) request that was sent by the server includes an [`Access-Control-Allow-Headers`](../../headers/access-control-allow-headers) header which includes at least one invalid header name.

The `Access-Control-Allow-Headers` header is sent by the server in response to a [preflight request](https://developer.mozilla.org/en-US/docs/Glossary/preflight_request); it lets the client know which [HTTP headers](../../headers) are permitted in CORS requests. If the client [user agent](https://developer.mozilla.org/en-US/docs/Glossary/user_agent) finds among the comma-delineated values provided by the header any header name it does not recognize, this error occurs.

This is a problem that most likely can only be fixed on the server side, by modifying the server's configuration to no longer send the invalid or unknown header name with the `Access-Control-Allow-Headers` header. It may also be worth checking to ensure that the user agent or HTTP library you're using on the client is up-to-date.

See also
--------

-   [CORS errors](../errors)
-   Glossary: [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS)
-   [CORS introduction](../../cors)
-   [HTTP headers](../../headers)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSInvalidAllowHeader$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSInvalidAllowHeader" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSInvalidAllowHeader</a>
