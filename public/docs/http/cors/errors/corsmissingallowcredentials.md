Errors: CORSMIssingAllowCredentials
===================================

Reason
------

    Reason: expected ‘true’ in CORS header ‘Access-Control-Allow-Credentials’

What went wrong?
----------------

The [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) request requires that the server permit the use of credentials, but the server's [`Access-Control-Allow-Credentials`](../../headers/access-control-allow-credentials) header's value isn't set to `true` to enable their use.

To fix this problem on the client side, revise the code to not request the use of credentials.

-   If the request is being issued using [`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest), make sure you're not setting [`withCredentials`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/withCredentials) to `true`.
-   If using [Server-sent events](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events), make sure [`EventSource.withCredentials`](https://developer.mozilla.org/en-US/docs/Web/API/EventSource/withCredentials) is `false` (it's the default value).
-   If using the [Fetch API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API), make sure [`Request.credentials`](https://developer.mozilla.org/en-US/docs/Web/API/Request/credentials) is `"omit"`.

To eliminate this error by changing the server's configuration, adjust the server's configuration to set the `Access-Control-Allow-Credentials` header's value to `true`.

See also
--------

-   [CORS errors](../errors)
-   Glossary: [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS)
-   [CORS introduction](../../cors)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSMIssingAllowCredentials$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSMIssingAllowCredentials" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSMIssingAllowCredentials</a>
