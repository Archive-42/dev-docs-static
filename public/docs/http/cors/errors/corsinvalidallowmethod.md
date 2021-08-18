Errors: CORSInvalidAllowMethod
==============================

Reason
------

    Reason: invalid token ‘xyz’ in CORS header ‘Access-Control-Allow-Methods’

What went wrong?
----------------

The response to the [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) request that was sent by the server includes an [`Access-Control-Allow-Methods`](../../headers/access-control-allow-methods) header which includes at least one invalid method name.

The `Access-Control-Allow-Methods` header is sent by the server to let the client know what [HTTP request methods](../../methods) it supports for CORS requests. The header's value is a comma-delineated string of HTTP method names, such as [`GET`](../../methods/get), [`POST`](../../methods/post), or [`HEAD`](../../methods/head). If any of the specified values are not recognized by the client [user agent](https://developer.mozilla.org/en-US/docs/Glossary/user_agent), this error occurs.

This is a problem that most likely can only be fixed on the server side, by modifying the server's configuration to no longer send the invalid or unknown method name with the `Access-Control-Allow-Methods` header. It may also be worth checking to ensure that the user agent or HTTP library you're using on the client is up-to-date.

See also
--------

-   [CORS errors](../errors)
-   Glossary: [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS)
-   [CORS introduction](../../cors)
-   [HTTP request methods](../../methods)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSInvalidAllowMethod$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSInvalidAllowMethod" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSInvalidAllowMethod</a>
