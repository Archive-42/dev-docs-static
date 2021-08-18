HTTP
====

**Hypertext Transfer Protocol (HTTP)** is an [application-layer](https://en.wikipedia.org/wiki/Application_Layer) protocol for transmitting hypermedia documents, such as HTML. It was designed for communication between web browsers and web servers, but it can also be used for other purposes. HTTP follows a classical [client-server model](https://en.wikipedia.org/wiki/Client%E2%80%93server_model), with a client opening a connection to make a request, then waiting until it receives a response. HTTP is a [stateless protocol](https://en.wikipedia.org/wiki/Stateless_protocol), meaning that the server does not keep any data (state) between two requests. Though often based on a TCP/IP layer, it can be used on any reliable [transport layer](https://en.wikipedia.org/wiki/Transport_Layer), that is, a protocol that doesn't lose messages silently like UDP does. [RUDP](https://en.wikipedia.org/wiki/Reliable_User_Datagram_Protocol) — the reliable update of UDP — is a suitable alternative.

Tutorials
---------

Learn how to use HTTP with guides and tutorials.

[Overview of HTTP](overview)  
The basic features of the client-server protocol: what it can do and its intended uses.

[HTTP Cache](caching)  
Caching is very important for fast Web sites. This article describes different methods of caching and how to use HTTP Headers to control them.

[HTTP Cookies](cookies)  
How cookies work is defined by [RFC 6265](https://tools.ietf.org/html/rfc6265). When serving an HTTP request, a server can send a `Set-Cookie` HTTP header with the response. The client then returns the cookie's value with every request to the same server in the form of a `Cookie` request header. The cookie can also be set to expire on a certain date, or restricted to a specific domain and path.

[Cross-Origin Resource Sharing (CORS)](cors)  
**Cross-site HTTP requests** are HTTP requests for resources from a **different domain** than the domain of the resource making the request. For instance, an HTML page from Domain A (`http://domaina.example/`) makes a request for an image on Domain B (`http://domainb.foo/image.jpg`) via the `img` element. Web pages today very commonly load cross-site resources, including CSS stylesheets, images, scripts, and other resources. CORS allows web developers to control how their site reacts to cross-site requests.

<!-- -->

[Evolution of HTTP](basics_of_http/evolution_of_http)  
A brief description of the changes between the early versions of HTTP, to the modern HTTP/2, the emergent HTTP/3 and beyond.

[Mozilla web security guidelines](https://wiki.mozilla.org/Security/Guidelines/Web_Security)  
A collection of tips to help operational teams with creating secure web applications.

<!-- -->

[HTTP Messages](messages)  
Describes the type and structure of the different kind of messages of HTTP/1.x and HTTP/2.

[A typical HTTP session](session)  
Shows and explains the flow of a usual HTTP session.

[Connection management in HTTP/1.x](connection_management_in_http_1.x)  
Describes the three connection management models available in HTTP/1.x, their strengths, and their weaknesses.

Reference
---------

Browse through detailed HTTP reference documentation.

[HTTP Headers](headers)  
HTTP message headers are used to describe a resource, or the behavior of the server or the client. Custom proprietary headers can be added using the `X-` prefix; others in an [IANA registry](https://www.iana.org/assignments/message-headers/message-headers.xhtml#perm-headers), whose original content was defined in [RFC 4229](https://tools.ietf.org/html/rfc4229). IANA also maintains a [registry of proposed new HTTP message headers](https://www.iana.org/assignments/message-headers/message-headers.xhtml#prov-headers).

[HTTP Request Methods](methods)  
The different operations that can be done with HTTP: [`GET`](methods/get), [`POST`](methods/post), and also less common requests like [`OPTIONS`](methods/options), [`DELETE`](methods/delete), or [`TRACE`](methods/trace).

[HTTP Status Response Codes](response_codes)  
HTTP response codes indicate whether a specific HTTP request has been successfully completed. Responses are grouped in five classes: informational responses, successful responses, redirections, client errors, and servers errors.

<!-- -->

[CSP directives](headers/content-security-policy)  
The [`Content-Security-Policy`](headers/content-security-policy) response header fields allows web site administrators to control resources the user agent is allowed to load for a given page. With a few exceptions, policies mostly involve specifying server origins and script endpoints.

Tools & resources
-----------------

Helpful tools and resources for understanding and debugging HTTP.

[Firefox Developer Tools](https://developer.mozilla.org/en-US/docs/Tools)  
[Network monitor](https://developer.mozilla.org/en-US/docs/Tools/Network_Monitor)

[Mozilla Observatory](https://observatory.mozilla.org/)  
A project designed to help developers, system administrators, and security professionals configure their sites safely and securely.

[RedBot](https://redbot.org/)  
Tools to check your cache-related headers

[How Browsers Work](https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/)  
A very comprehensive article on browser internals and request flow through HTTP protocol. A MUST-READ for any web developer.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP</a>
