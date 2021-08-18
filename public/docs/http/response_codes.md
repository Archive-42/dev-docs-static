Response codes
==============

HTTP response status codes indicate whether a specific [HTTP](index) request has been successfully completed. Responses are grouped in five classes:

1.  Informational responses (`100`–`199`)
2.  Successful responses (`200`–`299`)
3.  Redirects (`300`–`399`)
4.  Client errors (`400`–`499`)
5.  Server errors (`500`–`599`)

The below status codes are defined by [section 10 of RFC 2616](https://tools.ietf.org/html/rfc2616#section-10). You can find an updated specification in [RFC 7231](https://tools.ietf.org/html/rfc7231#section-6.5.1).

If you receive a response that is not in this list, it is a non-standard response, possibly custom to the server's software.

Information responses
---------------------

[`100 Continue`](status/100)  
This interim response indicates that everything so far is OK and that the client should continue the request, or ignore the response if the request is already finished.

[`101 Switching Protocol`](status/101)  
This code is sent in response to an [`Upgrade`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Upgrade) request header from the client, and indicates the protocol the server is switching to.

 [`102 Processing`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/102) ([WebDAV](https://developer.mozilla.org/en-US/docs/Glossary/WebDAV))  
This code indicates that the server has received and is processing the request, but no response is available yet.

[`103 Early Hints`](status/103)  
This status code is primarily intended to be used with the [`Link`](headers/link) header, letting the user agent start [preloading](https://developer.mozilla.org/en-US/docs/Web/HTML/Preloading_content) resources while the server prepares a response.

Successful responses
--------------------

[`200 OK`](status/200)  
The request has succeeded. The meaning of the success depends on the HTTP method:

-   `GET`: The resource has been fetched and is transmitted in the message body.
-   `HEAD`: The entity headers are in the message body.
-   `PUT` or `POST`: The resource describing the result of the action is transmitted in the message body.
-   `TRACE`: The message body contains the request message as received by the server.

[`201 Created`](status/201)  
The request has succeeded and a new resource has been created as a result. This is typically the response sent after `POST` requests, or some `PUT` requests.

[`202 Accepted`](status/202)  
The request has been received but not yet acted upon. It is noncommittal, since there is no way in HTTP to later send an asynchronous response indicating the outcome of the request. It is intended for cases where another process or server handles the request, or for batch processing.

[`203 Non-Authoritative Information`](status/203)  
This response code means the returned meta-information is not exactly the same as is available from the origin server, but is collected from a local or a third-party copy. This is mostly used for mirrors or backups of another resource. Except for that specific case, the "200 OK" response is preferred to this status.

[`204 No Content`](status/204)  
There is no content to send for this request, but the headers may be useful. The user-agent may update its cached headers for this resource with the new ones.

[`205 Reset Content`](status/205)  
Tells the user-agent to reset the document which sent this request.

[`206 Partial Content`](status/206)  
This response code is used when the [`Range`](headers/range) header is sent from the client to request only part of a resource.

 [`207 Multi-Status`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/207) ([WebDAV](https://developer.mozilla.org/en-US/docs/Glossary/WebDAV))  
Conveys information about multiple resources, for situations where multiple status codes might be appropriate.

 [`208 Already Reported`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/208) ([WebDAV](https://developer.mozilla.org/en-US/docs/Glossary/WebDAV))  
Used inside a `<dav:propstat>` response element to avoid repeatedly enumerating the internal members of multiple bindings to the same collection.

 [`226 IM Used`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/226) ([HTTP Delta encoding](https://tools.ietf.org/html/rfc3229))  
The server has fulfilled a `GET` request for the resource, and the response is a representation of the result of one or more instance-manipulations applied to the current instance.

Redirection messages
--------------------

[`300 Multiple Choice`](status/300)  
The request has more than one possible response. The user-agent or user should choose one of them. (There is no standardized way of choosing one of the responses, but HTML links to the possibilities are recommended so the user can pick.)

[`301 Moved Permanently`](status/301)  
The URL of the requested resource has been changed permanently. The new URL is given in the response.

[`302 Found`](status/302)  
This response code means that the URI of requested resource has been changed *temporarily*. Further changes in the URI might be made in the future. Therefore, this same URI should be used by the client in future requests.

[`303 See Other`](status/303)  
The server sent this response to direct the client to get the requested resource at another URI with a GET request.

[`304 Not Modified`](status/304)  
This is used for caching purposes. It tells the client that the response has not been modified, so the client can continue to use the same cached version of the response.

 `305 Use Proxy`   
Defined in a previous version of the HTTP specification to indicate that a requested response must be accessed by a proxy. It has been deprecated due to security concerns regarding in-band configuration of a proxy.

`306 unused`  
This response code is no longer used; it is just reserved. It was used in a previous version of the HTTP/1.1 specification.

[`307 Temporary Redirect`](status/307)  
The server sends this response to direct the client to get the requested resource at another URI with same method that was used in the prior request. This has the same semantics as the `302 Found` HTTP response code, with the exception that the user agent *must not* change the HTTP method used: If a `POST` was used in the first request, a `POST` must be used in the second request.

[`308 Permanent Redirect`](status/308)  
This means that the resource is now permanently located at another URI, specified by the `Location:` HTTP Response header. This has the same semantics as the `301 Moved Permanently` HTTP response code, with the exception that the user agent *must not* change the HTTP method used: If a `POST` was used in the first request, a `POST` must be used in the second request.

Client error responses
----------------------

[`400 Bad Request`](status/400)  
The server could not understand the request due to invalid syntax.

[`401 Unauthorized`](status/401)  
Although the HTTP standard specifies "unauthorized", semantically this response means "unauthenticated". That is, the client must authenticate itself to get the requested response.

 [`402 Payment Required`](status/402)   
This response code is reserved for future use. The initial aim for creating this code was using it for digital payment systems, however this status code is used very rarely and no standard convention exists.

[`403 Forbidden`](status/403)  
The client does not have access rights to the content; that is, it is unauthorized, so the server is refusing to give the requested resource. Unlike 401, the client's identity is known to the server.

[`404 Not Found`](status/404)  
The server can not find the requested resource. In the browser, this means the URL is not recognized. In an API, this can also mean that the endpoint is valid but the resource itself does not exist. Servers may also send this response instead of 403 to hide the existence of a resource from an unauthorized client. This response code is probably the most famous one due to its frequent occurrence on the web.

[`405 Method Not Allowed`](status/405)  
The request method is known by the server but has been disabled and cannot be used. For example, an API may forbid DELETE-ing a resource. The two mandatory methods, `GET` and `HEAD`, must never be disabled and should not return this error code.

[`406 Not Acceptable`](status/406)  
This response is sent when the web server, after performing [server-driven content negotiation](https://developer.mozilla.org/en-US/docs/HTTP/Content_negotiation#Server-driven_negotiation), doesn't find any content that conforms to the criteria given by the user agent.

[`407 Proxy Authentication Required`](status/407)  
This is similar to 401 but authentication is needed to be done by a proxy.

[`408 Request Timeout`](status/408)  
This response is sent on an idle connection by some servers, even without any previous request by the client. It means that the server would like to shut down this unused connection. This response is used much more since some browsers, like Chrome, Firefox 27+, or IE9, use HTTP pre-connection mechanisms to speed up surfing. Also note that some servers merely shut down the connection without sending this message.

[`409 Conflict`](status/409)  
This response is sent when a request conflicts with the current state of the server.

[`410 Gone`](status/410)  
This response is sent when the requested content has been permanently deleted from server, with no forwarding address. Clients are expected to remove their caches and links to the resource. The HTTP specification intends this status code to be used for "limited-time, promotional services". APIs should not feel compelled to indicate resources that have been deleted with this status code.

[`411 Length Required`](status/411)  
Server rejected the request because the `Content-Length` header field is not defined and the server requires it.

[`412 Precondition Failed`](status/412)  
The client has indicated preconditions in its headers which the server does not meet.

[`413 Payload Too Large`](status/413)  
Request entity is larger than limits defined by server; the server might close the connection or return an `Retry-After` header field.

[`414 URI Too Long`](status/414)  
The URI requested by the client is longer than the server is willing to interpret.

[`415 Unsupported Media Type`](status/415)  
The media format of the requested data is not supported by the server, so the server is rejecting the request.

[`416 Range Not Satisfiable`](status/416)  
The range specified by the `Range` header field in the request can't be fulfilled; it's possible that the range is outside the size of the target URI's data.

[`417 Expectation Failed`](status/417)  
This response code means the expectation indicated by the `Expect` request header field can't be met by the server.

[`418 I'm a teapot`](status/418)  
The server refuses the attempt to brew coffee with a teapot.

[`421 Misdirected Request`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/421)  
The request was directed at a server that is not able to produce a response. This can be sent by a server that is not configured to produce responses for the combination of scheme and authority that are included in the request URI.

 [`422 Unprocessable Entity`](status/422) ([WebDAV](https://developer.mozilla.org/en-US/docs/Glossary/WebDAV))  
The request was well-formed but was unable to be followed due to semantic errors.

 [`423 Locked`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/423) ([WebDAV](https://developer.mozilla.org/en-US/docs/Glossary/WebDAV))  
The resource that is being accessed is locked.

 [`424 Failed Dependency`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/424) ([WebDAV](https://developer.mozilla.org/en-US/docs/Glossary/WebDAV))  
The request failed due to failure of a previous request.

 [`425 Too Early`](status/425)   
Indicates that the server is unwilling to risk processing a request that might be replayed.

[`426 Upgrade Required`](status/426)  
The server refuses to perform the request using the current protocol but might be willing to do so after the client upgrades to a different protocol. The server sends an [`Upgrade`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Upgrade) header in a 426 response to indicate the required protocol(s).

[`428 Precondition Required`](status/428)  
The origin server requires the request to be conditional. This response is intended to prevent the 'lost update' problem, where a client GETs a resource's state, modifies it, and PUTs it back to the server, when meanwhile a third party has modified the state on the server, leading to a conflict.

[`429 Too Many Requests`](status/429)  
The user has sent too many requests in a given amount of time ("rate limiting").

[`431 Request Header Fields Too Large`](status/431)  
The server is unwilling to process the request because its header fields are too large. The request may be resubmitted after reducing the size of the request header fields.

[`451 Unavailable For Legal Reasons`](status/451)  
The user-agent requested a resource that cannot legally be provided, such as a web page censored by a government.

Server error responses
----------------------

[`500 Internal Server Error`](status/500)  
The server has encountered a situation it doesn't know how to handle.

[`501 Not Implemented`](status/501)  
The request method is not supported by the server and cannot be handled. The only methods that servers are required to support (and therefore that must not return this code) are `GET` and `HEAD`.

[`502 Bad Gateway`](status/502)  
This error response means that the server, while working as a gateway to get a response needed to handle the request, got an invalid response.

[`503 Service Unavailable`](status/503)  
The server is not ready to handle the request. Common causes are a server that is down for maintenance or that is overloaded. Note that together with this response, a user-friendly page explaining the problem should be sent. This responses should be used for temporary conditions and the `Retry-After:` HTTP header should, if possible, contain the estimated time before the recovery of the service. The webmaster must also take care about the caching-related headers that are sent along with this response, as these temporary condition responses should usually not be cached.

[`504 Gateway Timeout`](status/504)  
This error response is given when the server is acting as a gateway and cannot get a response in time.

[`505 HTTP Version Not Supported`](status/505)  
The HTTP version used in the request is not supported by the server.

[`506 Variant Also Negotiates`](status/506)  
The server has an internal configuration error: the chosen variant resource is configured to engage in transparent content negotiation itself, and is therefore not a proper end point in the negotiation process.

 [`507 Insufficient Storage`](status/507) ([WebDAV](https://developer.mozilla.org/en-US/docs/Glossary/WebDAV))  
The method could not be performed on the resource because the server is unable to store the representation needed to successfully complete the request.

 [`508 Loop Detected`](status/508) ([WebDAV](https://developer.mozilla.org/en-US/docs/Glossary/WebDAV))  
The server detected an infinite loop while processing the request.

[`510 Not Extended`](status/510)  
Further extensions to the request are required for the server to fulfil it.

[`511 Network Authentication Required`](status/511)  
The 511 status code indicates that the client needs to authenticate to gain network access.

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

[`100`](status/100)

Yes

12

Yes

Yes

Yes

Yes

[`200`](status/200)

Yes

12

Yes

Yes

Yes

Yes

[`201`](status/201)

Yes

12

Yes

Yes

Yes

Yes

[`204`](status/204)

Yes

12

Yes

Yes

Yes

Yes

[`206`](status/206)

Yes

12

Yes

Yes

Yes

Yes

[`301`](status/301)

Yes

12

Yes

Yes

Yes

Yes

[`302`](status/302)

Yes

12

Yes

Yes

Yes

Yes

[`303`](status/303)

Yes

12

Yes

Yes

Yes

Yes

[`304`](status/304)

Yes

12

Yes

Yes

Yes

Yes

[`307`](status/307)

Yes

12

Yes

Yes

Yes

Yes

[`308`](status/308)

36

12

14

11

 11   
Does not work below Windows 10.

24

7

[`401`](status/401)

Yes

12

Yes

Yes

Yes

Yes

[`403`](status/403)

Yes

12

Yes

Yes

Yes

Yes

[`404`](status/404)

Yes

12

Yes

Yes

Yes

Yes

[`406`](status/406)

Yes

12

Yes

Yes

Yes

Yes

[`407`](status/407)

Yes

12

Yes

Yes

Yes

Yes

[`409`](status/409)

Yes

12

Yes

Yes

Yes

Yes

[`410`](status/410)

Yes

12

Yes

Yes

Yes

Yes

[`412`](status/412)

Yes

12

Yes

Yes

Yes

Yes

[`416`](status/416)

Yes

12

Yes

Yes

Yes

Yes

[`418`](status/418)

Yes

12

Yes

Yes

Yes

Yes

[`425`](status/425)

?

?

58

?

?

?

[`451`](status/451)

Yes

12

Yes

Yes

Yes

Yes

[`500`](status/500)

Yes

12

Yes

Yes

Yes

Yes

[`501`](status/501)

Yes

12

Yes

Yes

Yes

Yes

[`502`](status/502)

Yes

12

Yes

Yes

Yes

Yes

[`503`](status/503)

Yes

12

Yes

Yes

Yes

Yes

[`504`](status/504)

Yes

12

Yes

Yes

Yes

Yes

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

[`100`](status/100)

Yes

Yes

Yes

Yes

Yes

Yes

[`200`](status/200)

Yes

Yes

Yes

Yes

Yes

Yes

[`201`](status/201)

Yes

Yes

Yes

Yes

Yes

Yes

[`204`](status/204)

Yes

Yes

Yes

Yes

Yes

Yes

[`206`](status/206)

Yes

Yes

Yes

Yes

Yes

Yes

[`301`](status/301)

Yes

Yes

Yes

Yes

Yes

Yes

[`302`](status/302)

Yes

Yes

Yes

Yes

Yes

Yes

[`303`](status/303)

Yes

Yes

Yes

Yes

Yes

Yes

[`304`](status/304)

Yes

Yes

Yes

Yes

Yes

Yes

[`307`](status/307)

Yes

Yes

Yes

Yes

Yes

Yes

[`308`](status/308)

37

36

14

24

7

3.0

[`401`](status/401)

Yes

Yes

Yes

Yes

Yes

Yes

[`403`](status/403)

Yes

Yes

Yes

Yes

Yes

Yes

[`404`](status/404)

Yes

Yes

Yes

Yes

Yes

Yes

[`406`](status/406)

Yes

Yes

Yes

Yes

Yes

Yes

[`407`](status/407)

Yes

Yes

Yes

Yes

Yes

Yes

[`409`](status/409)

Yes

Yes

Yes

Yes

Yes

Yes

[`410`](status/410)

Yes

Yes

Yes

Yes

Yes

Yes

[`412`](status/412)

Yes

Yes

Yes

Yes

Yes

Yes

[`416`](status/416)

Yes

Yes

Yes

Yes

Yes

Yes

[`418`](status/418)

Yes

Yes

Yes

Yes

Yes

Yes

[`425`](status/425)

?

?

58

?

?

?

[`451`](status/451)

Yes

Yes

Yes

Yes

Yes

Yes

[`500`](status/500)

Yes

Yes

Yes

Yes

Yes

Yes

[`501`](status/501)

Yes

Yes

Yes

Yes

Yes

Yes

[`502`](status/502)

Yes

Yes

Yes

Yes

Yes

Yes

[`503`](status/503)

Yes

Yes

Yes

Yes

Yes

Yes

[`504`](status/504)

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [List of HTTP status codes on Wikipedia](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes)
-   [IANA official registry of HTTP status codes](http://www.iana.org/assignments/http-status-codes/http-status-codes.xhtml)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Response_codes$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Response_codes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Response_codes</a>
