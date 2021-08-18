Errors: CORSNotSupportingCredentials
====================================

Reason
------

    Reason: Credential is not supported if the CORS header ‘Access-Control-Allow-Origin’ is ‘*’

What went wrong?
----------------

The [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) request was attempted with the credentials flag set, but the server is configured using the wildcard (`"*"`) as the value of [`Access-Control-Allow-Origin`](../../headers/access-control-allow-origin), which doesn't allow the use of credentials.

To correct this problem on the client side, simply ensure that the credentials flag's value is `false` when issuing your CORS request.

-   If the request is being issued using [`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest), make sure you're not setting [`withCredentials`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/withCredentials) to `true`.
-   If using [Server-sent events](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events), make sure [`EventSource.withCredentials`](https://developer.mozilla.org/en-US/docs/Web/API/EventSource/withCredentials) is `false` (it's the default value).
-   If using the [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API), make sure [`Request.credentials`](https://developer.mozilla.org/en-US/docs/Web/API/Request/credentials) is `"omit"`.

If, instead, you need to adjust the server's behavior, you'll need to change the value of `Access-Control-Allow-Origin` to grant access to the origin from which the client is loaded.

See also
--------

-   [CORS errors](../errors)
-   Glossary: [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS)
-   [CORS introduction](../../cors)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSNotSupportingCredentials$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSNotSupportingCredentials" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSNotSupportingCredentials</a>
