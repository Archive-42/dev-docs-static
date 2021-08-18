Errors: CORSOriginHeaderNotAdded
================================

Reason
------

    Reason: CORS header ‘Origin’ cannot be added

What went wrong?
----------------

The [user agent](https://developer.mozilla.org/en-US/docs/Glossary/user_agent) was unable to add the required [`Origin`](../../headers/origin) header to the [HTTP](https://developer.mozilla.org/en-US/docs/Glossary/HTTP) request. All CORS requests must have an `Origin` header.

This can happen if the JavaScript code is running with enhanced privileges allowing it access to multiple domains' content, for example.

See also
--------

-   [CORS errors](../errors)
-   Glossary: [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS)
-   [CORS introduction](../../cors)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSOriginHeaderNotAdded$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSOriginHeaderNotAdded" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSOriginHeaderNotAdded</a>
