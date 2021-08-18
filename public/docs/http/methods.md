Methods
=======

HTTP defines a set of **request methods** to indicate the desired action to be performed for a given resource. Although they can also be nouns, these request methods are sometimes referred to as *HTTP verbs*. Each of them implements a different semantic, but some common features are shared by a group of them: e.g. a request method can be [safe](https://developer.mozilla.org/en-US/docs/Glossary/safe), [idempotent](https://developer.mozilla.org/en-US/docs/Glossary/idempotent), or [cacheable](https://developer.mozilla.org/en-US/docs/Glossary/cacheable).

`GET`  
The `GET` method requests a representation of the specified resource. Requests using `GET` should only retrieve data.

`HEAD`  
The `HEAD` method asks for a response identical to that of a `GET` request, but without the response body.

`POST`  
The `POST` method is used to submit an entity to the specified resource, often causing a change in state or side effects on the server.

`PUT`  
The `PUT` method replaces all current representations of the target resource with the request payload.

`DELETE`  
The `DELETE` method deletes the specified resource.

`CONNECT`  
The `CONNECT` method establishes a tunnel to the server identified by the target resource.

`OPTIONS`  
The `OPTIONS` method is used to describe the communication options for the target resource.

`TRACE`  
The `TRACE` method performs a message loop-back test along the path to the target resource.

`PATCH`  
The `PATCH` method is used to apply partial modifications to a resource.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Title</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://tools.ietf.org/html/rfc7231#section-4">RFC 7231, section 4: Request methods</a></td><td>Hypertext Transfer Protocol (HTTP/1.1): Semantics and Content</td><td>Specifies GET, HEAD, POST, PUT, DELETE, CONNECT, OPTIONS, TRACE.</td></tr><tr class="even"><td><a href="https://tools.ietf.org/html/rfc5789#section-2">RFC 5789, section 2: Patch method</a></td><td>PATCH Method for HTTP</td><td>Specifies PATCH.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found. Please contribute data for "http/methods" (depth: 1) to the [MDN compatibility data repository](https://github.com/mdn/browser-compat-data).

See also
--------

-   [HTTP headers](headers)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods</a>
