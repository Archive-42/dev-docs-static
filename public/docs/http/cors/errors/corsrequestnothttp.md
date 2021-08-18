Errors: CORSRequestNotHttp
==========================

Reason
------

    Reason: CORS request not HTTP

What went wrong?
----------------

[CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS) requests may only use the HTTPS URL scheme, but the URL specified by the request is of a different type. This often occurs if the URL specifies a local file, using a `file:///` URL.

To fix this problem, simply make sure you use HTTPS URLs when issuing requests involving CORS, such as [`XMLHttpRequest`](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest), [Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API) APIs, Web Fonts (`@font-face`), and [WebGL textures](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Using_textures_in_WebGL), and XSL stylesheets.

### Local File Security in Firefox 68

When a user opened a page using a `file:///` URI in Firefox 67 and earlier, the origin of the page was defined as the directory from which the page was opened. Resources in the same directory and its subdirectories were treated as having the same origin for purposes of the CORS same-origin rule.

In response to [CVE-2019-11730](https://www.mozilla.org/en-US/security/advisories/mfsa2019-21/#CVE-2019-11730), Firefox 68 and later define the origin of a page opened using a `file:///` URI as unique. Therefore, other resources in the same directory or its subdirectories no longer satisfy the CORS same-origin rule. This new behavior is enabled by default using the `privacy.file_unique_origin` preference.

See also
--------

-   [CORS errors](../errors)
-   Glossary: [CORS](https://developer.mozilla.org/en-US/docs/Glossary/CORS)
-   [CORS introduction](../../cors)
-   [What is a URL?](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_is_a_URL)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSRequestNotHttp$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSRequestNotHttp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS/Errors/CORSRequestNotHttp</a>
