Errors: CORSPreflightDidNotSucceed
==================================

Reason
------

    Reason: CORS preflight channel did not succeed

What went wrong?
----------------

The [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) request requires preflight, preflighting could not be performed. There are a couple of reasons why preflighting might fail:

-   A cross-site request has previously been performed that already did a preflight, and doing the preflight again is not permitted. Make sure your code only preflights once per connection.
-   The preflight request simply suffered any kind of networking error that might ordinarily occur.

See also
--------

-   [CORS errors](../errors)
-   Glossary: [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS)
-   [CORS introduction](../../cors)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSPreflightDidNotSucceed$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSPreflightDidNotSucceed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSPreflightDidNotSucceed</a>
