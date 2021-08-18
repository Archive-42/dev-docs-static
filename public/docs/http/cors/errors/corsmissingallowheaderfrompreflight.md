Errors: CORSMissingAllowHeaderFromPreflight
===========================================

Reason
------

    Reason: missing token ‘xyz’ in CORS header ‘Access-Control-Allow-Headers’ from CORS preflight channel

What went wrong?
----------------

The `Access-Control-Allow-Headers` header is sent by the server to let the client know which headers it supports for [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) requests. The value of `Access-Control-Allow-Headers` should be a comma-delineated list of header names, such as "`X-Custom-Information`" or any of the standard but non-basic header names (which are always allowed).

This error occurs when attempting to preflight a header that is not expressly allowed (that is, it's not included in the list specified by the `Access-Control-Allow-Headers` header sent by the server). To fix this, the server needs to be updated so that it allows the indicated header, or you need to avoid using that header.

See also
--------

-   [CORS errors](../errors)
-   Glossary: [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS)
-   [CORS introduction](../../cors)
-   [HTTP headers](../../headers)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSMissingAllowHeaderFromPreflight$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSMissingAllowHeaderFromPreflight" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSMissingAllowHeaderFromPreflight</a>
