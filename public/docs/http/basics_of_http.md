Basics of HTTP
==============

HTTP is an extensible protocol that relies on concepts like resources and Uniform Resource Identifiers (URIs), simple message structure, and client-server communication flow. On top of these basic concepts, numerous extensions have been developed over the years that add updated functionality and semantics with new HTTP methods or headers.

Articles
--------

[Overview of HTTP](overview)  
Describes what HTTP is and its role in web architecture, including its position in the protocol stack.

[Evolution of HTTP](basics_of_http/evolution_of_http)  
HTTP was created in the early 1990s and has been extended several times. This article goes through its history and describes HTTP/0.9, HTTP/1.0, HTTP/1.1, and the modern HTTP/2, as well as novelties introduced over the years.

[Resources and URIs](resources_and_uris)  
A brief introduction to the concept of resources, identifiers, and locations on the web.

[Identifying resources on the Web](basics_of_http/identifying_resources_on_the_web)  
Describes how web resources are referenced and how to locate them.

[Data URIs](basics_of_http/data_uris)  
A specific kind of URI that directly embeds the resource it represents. Data URIs are very convenient, but have some caveats.

 [Resource URLs](basics_of_http/resource_urls)   
Resource URLs, those prefixed with the `resource` scheme are used by Firefox and Firefox browser extensions to load resources internally, but is also available to some sites the browser connects to as well.

Separating identity and location of a resource: The Alt-Svc HTTP header  
Most of the time the identity and location of a web resource are shared, this can be changed with the [`Alt-Svc`](headers/alt-svc) header.

[MIME types](basics_of_http/mime_types)  
Since HTTP/1.0, different types of content can be transmitted. This article explains how this is accomplished using the [`Content-Type`](headers/content-type) header and the MIME standard.

[Choosing between www and non-www URLs](basics_of_http/choosing_between_www_and_non-www_urls)  
This article provides guidance on how to choose whether to use a www-prefixed domain or not, along with the consequences of that choice.

[Flow of an HTTP session](flow_of_an_http_session)  
This fundamental article describes a typical HTTP session: What happens under the hood when you click on a link in your browser.

[HTTP Messages](messages)  
HTTP Messages transmitted during requests or responses have a very clear structure. This introductory article describes this structure, its purpose, and its possibilities.

[Frame and message structure in HTTP/2](frame%20and%20message%20structure%20in%20http_2)  
HTTP/2 encapsulates and represents HTTP/1.x messages in a binary frame. This article explains the frame structure, its purpose, and the way it's encoded.

[Connection management in HTTP/1.x](connection_management_in_http_1.x)  
HTTP/1.1 was the first version of HTTP to support persistent connection and pipelining. This article explains both concepts.

[Connection management in HTTP/2](connection_management_in_http_2)  
HTTP/2 completely revisited how connections are created and maintained. This article explains how HTTP frames allow multiplexing and solve the 'head-of-line' blocking problem of former HTTP versions.

[Content Negotiation](content_negotiation)  
HTTP introduces a set of headers, starting with `Accept` as a way for a browser to announce the format, language, or encoding it prefers. This article explains how this advertisement happens, how the server is expected to react, and how it chooses the most adequate response.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP</a>
