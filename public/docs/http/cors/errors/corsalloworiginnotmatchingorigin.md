Errors: CORSAllowOriginNotMatchingOrigin
========================================

Reason
------

    Reason: CORS header 'Access-Control-Allow-Origin' does not match 'xyz'

What went wrong?
----------------

Simply put, the origin making the request does not match any of the origins permitted by the [`Access-Control-Allow-Origin`](../../headers/access-control-allow-origin) header.

This error can also occur if the response includes more than one `Access-Control-Allow-Origin` header.

If the service your code is accessing using a CORS request is under your control, make sure that it's configured to include your origin in its `Access-Control-Allow-Origin` header, and that only one such header is included in responses. The header itself accepts a comma-delineated list of origins, so adding a new origin is not difficult.

For example, in Apache, add a line such as the following to the server's configuration (within the appropriate `<Directory>`, `<Location>`, `<Files>`, or `<VirtualHost>` section). The configuration is typically found in a `.conf` file (`httpd.conf` and `apache.conf` are common names for these), or in an `.htaccess` file.

    Header set Access-Control-Allow-Origin 'origin-list'

For Nginx, the command to set up this header is:

    add_header 'Access-Control-Allow-Origin' 'origin-list'

See also
--------

-   [CORS errors](../errors)
-   Glossary: [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS)
-   [CORS introduction](../../cors)
-   [Enable CORS: I want to add CORS support to my server](https://enable-cors.org/server.html)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSAllowOriginNotMatchingOrigin$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSAllowOriginNotMatchingOrigin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSAllowOriginNotMatchingOrigin</a>
