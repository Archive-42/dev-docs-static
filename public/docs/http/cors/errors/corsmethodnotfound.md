Errors: CORSMethodNotFound
==========================

Reason
------

    Reason: Did not find method in CORS header ‘Access-Control-Allow-Methods’

What went wrong?
----------------

The HTTP method being used by the [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) request is not included in the list of methods specified by the response's [`Access-Control-Allow-Methods`](../../headers/access-control-allow-methods) header. This header specifies a comma-delineated list of the HTTP methods which may be used when using CORS to access the URL specified in the request; if the request is using any other method, this error occurs.

For example, if the response includes:

    Access-Control-Allow-Methods: GET,HEAD,POST

Trying to use a [`PUT`](../../methods/put) request will fail with this error.

Make sure your code only uses the permitted HTTP methods when accessing the service.

**Note:** If the server includes any unrecognized or undefined method names in its `Access-Control-Allow-methods` header, a different error occurs: `Reason: invalid token ‘xyz' in CORS header ‘Access-Control-Allow-Methods’`.

See also
--------

-   [CORS errors](../errors)
-   Glossary: [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS)
-   [CORS introduction](../../cors)
-   [HTTP request methods](../../methods)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSMethodNotFound$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSMethodNotFound" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSMethodNotFound</a>
