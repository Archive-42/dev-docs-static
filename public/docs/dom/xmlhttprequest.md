XMLHttpRequest
==============

`XMLHttpRequest` (XHR) objects are used to interact with servers. You can retrieve data from a URL without having to do a full page refresh. This enables a Web page to update just part of a page without disrupting what the user is doing. `XMLHttpRequest` is used heavily in [AJAX](https://developer.mozilla.org/en-US/docs/Glossary/AJAX) programming.

Despite its name, `XMLHttpRequest` can be used to retrieve any type of data, not just XML.

If your communication needs to involve receiving event data or message data from a server, consider using [server-sent events](server-sent_events) through the [`EventSource`](eventsource) interface. For full-duplex communication, [WebSockets](websockets_api) may be a better choice.

**Note:** This feature is available in [Web Workers](web_workers_api).

**Note**

Not supported in service workers.

Constructor
-----------

[`XMLHttpRequest()`](xmlhttprequest/xmlhttprequest)  
The constructor initializes an `XMLHttpRequest`. It must be called before any other method calls.

Properties
----------

*This interface also inherits properties of [`XMLHttpRequestEventTarget`](xmlhttprequesteventtarget) and of [`EventTarget`](eventtarget).*

[`XMLHttpRequest.onreadystatechange`](xmlhttprequest/onreadystatechange)  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that is called whenever the `readyState` attribute changes.

 [`XMLHttpRequest.readyState`](xmlhttprequest/readystate) <span class="badge inline readonly">Read only </span>   
Returns an `unsigned short`, the state of the request.

 [`XMLHttpRequest.response`](xmlhttprequest/response) <span class="badge inline readonly">Read only </span>   
Returns an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer), [`Blob`](blob), [`Document`](document), JavaScript object, or a [`DOMString`](domstring), depending on the value of [`XMLHttpRequest.responseType`](xmlhttprequest/responsetype), that contains the response entity body.

 [`XMLHttpRequest.responseText`](xmlhttprequest/responsetext) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) that contains the response to the request as text, or `null` if the request was unsuccessful or has not yet been sent.

[`XMLHttpRequest.responseType`](xmlhttprequest/responsetype)  
Is an enumerated value that defines the response type.

 [`XMLHttpRequest.responseURL`](xmlhttprequest/responseurl) <span class="badge inline readonly">Read only </span>   
Returns the serialized URL of the response or the empty string if the URL is null.

 [`XMLHttpRequest.responseXML`](xmlhttprequest/responsexml) <span class="badge inline readonly">Read only </span>   
Returns a [`Document`](document) containing the response to the request, or `null` if the request was unsuccessful, has not yet been sent, or cannot be parsed as XML or HTML. Not available in workers.

 [`XMLHttpRequest.status`](xmlhttprequest/status) <span class="badge inline readonly">Read only </span>   
Returns an `unsigned short` with the status of the response of the request.

 [`XMLHttpRequest.statusText`](xmlhttprequest/statustext) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) containing the response string returned by the HTTP server. Unlike [`XMLHttpRequest.status`](xmlhttprequest/status), this includes the entire text of the response message ("`200 OK`", for example).

**Note**
According to the HTTP/2 specification ([8.1.2.4](https://http2.github.io/http2-spec/#rfc.section.8.1.2.4) [Response Pseudo-Header Fields](https://http2.github.io/http2-spec/#HttpResponse)), HTTP/2 does not define a way to carry the version or reason phrase that is included in an HTTP/1.1 status line.

[`XMLHttpRequest.timeout`](xmlhttprequest/timeout)  
Is an `unsigned long` representing the number of milliseconds a request can take before automatically being terminated.

<span class="page-not-created">`XMLHttpRequestEventTarget.ontimeout`</span>  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that is called whenever the request times out.

 [`XMLHttpRequest.upload`](xmlhttprequest/upload) <span class="badge inline readonly">Read only </span>   
Is an <span class="page-not-created">`XMLHttpRequestUpload`</span>, representing the upload process.

[`XMLHttpRequest.withCredentials`](xmlhttprequest/withcredentials)  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether or not cross-site `Access-Control` requests should be made using credentials such as cookies or authorization headers.

### Non-standard properties

 [`XMLHttpRequest.channel`](xmlhttprequest/channel)<span class="badge inline readonly">Read only </span>   
The channel used by the object when performing the request.

 [`XMLHttpRequest.mozAnon`](xmlhttprequest/mozanon)<span class="badge inline readonly">Read only </span>   
Is a boolean. If true, the request will be sent without cookie and authentication headers.

 [`XMLHttpRequest.mozSystem`](xmlhttprequest/mozsystem)<span class="badge inline readonly">Read only </span>   
Is a boolean. If true, the same origin policy will not be enforced on the request.

[`XMLHttpRequest.mozBackgroundRequest`](xmlhttprequest/mozbackgroundrequest)  
Is a boolean. It indicates whether or not the object represents a background service request.

 [`XMLHttpRequest.mozResponseArrayBuffer`](xmlhttprequest/mozresponsearraybuffer) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline readonly">Read only </span>   
[`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer). The response to the request, as a JavaScript typed array.

 [`XMLHttpRequest.multipart`](xmlhttprequest/multipart) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
**This Gecko-only feature, a boolean, was removed in Firefox/Gecko 22.** Please use [Server-Sent Events](server-sent_events), [Web Sockets](websockets_api), or `responseText` from progress events instead.

### Event handlers

`onreadystatechange` as a property of the `XMLHttpRequest` instance is supported in all browsers.

Since then, a number of additional event handlers have been implemented in various browsers (`onload`, `onerror`, `onprogress`, etc.). See [Using XMLHttpRequest](xmlhttprequest/using_xmlhttprequest).

More recent browsers, including Firefox, also support listening to the `XMLHttpRequest` events via standard [`addEventListener()`](eventtarget/addeventlistener) APIs in addition to setting `on*` properties to a handler function.

Methods
-------

[`XMLHttpRequest.abort()`](xmlhttprequest/abort)  
Aborts the request if it has already been sent.

[`XMLHttpRequest.getAllResponseHeaders()`](xmlhttprequest/getallresponseheaders)  
Returns all the response headers, separated by [CRLF](https://developer.mozilla.org/en-US/docs/Glossary/CRLF), as a string, or `null` if no response has been received.

[`XMLHttpRequest.getResponseHeader()`](xmlhttprequest/getresponseheader)  
Returns the string containing the text of the specified header, or `null` if either the response has not yet been received or the header doesn't exist in the response.

[`XMLHttpRequest.open()`](xmlhttprequest/open)  
Initializes a request.

[`XMLHttpRequest.overrideMimeType()`](xmlhttprequest/overridemimetype)  
Overrides the MIME type returned by the server.

[`XMLHttpRequest.send()`](xmlhttprequest/send)  
Sends the request. If the request is asynchronous (which is the default), this method returns as soon as the request is sent.

[`XMLHttpRequest.setRequestHeader()`](xmlhttprequest/setrequestheader)  
Sets the value of an HTTP request header. You must call `setRequestHeader()`after [`open()`](#open), but before `send()`.

Events
------

[`abort`](xmlhttprequest/abort_event)  
Fired when a request has been aborted, for example because the program called [`XMLHttpRequest.abort()`](xmlhttprequest/abort).  
Also available via the [`onabort`](xmlhttprequesteventtarget/onabort) property.

[`error`](xmlhttprequest/error_event)  
Fired when the request encountered an error.  
Also available via the [`onerror`](xmlhttprequesteventtarget/onerror) property.

[`load`](xmlhttprequest/load_event)  
Fired when an [`XMLHttpRequest`](xmlhttprequest) transaction completes successfully.  
Also available via the [`onload`](xmlhttprequesteventtarget/onload) property.

[`loadend`](xmlhttprequest/loadend_event)  
Fired when a request has completed, whether successfully (after [`load`](xmlhttprequest/load_event)) or unsuccessfully (after [`abort`](xmlhttprequest/abort_event) or [`error`](xmlhttprequest/error_event)).  
Also available via the <span class="page-not-created">`onloadend`</span> property.

[`loadstart`](xmlhttprequest/loadstart_event)  
Fired when a request has started to load data.  
Also available via the [`onloadstart`](xmlhttprequesteventtarget/onloadstart) property.

[`progress`](xmlhttprequest/progress_event)  
Fired periodically when a request receives more data.  
Also available via the [`onprogress`](xmlhttprequesteventtarget/onprogress) property.

[`timeout`](xmlhttprequest/timeout_event)  
Fired when progress is terminated due to preset time expiring.  
Also available via the <span class="page-not-created">`ontimeout`</span> property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>Live standard, latest version</td></tr></tbody></table>

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`XMLHttpRequest`

1

12

1

7

5

Implemented via `ActiveXObject('Microsoft.XMLHTTP')`

8

1.2

1

18

4

10.1

1

1.0

`XMLHttpRequest`

1

12

1

7

≤12.1

3

1

18

4

≤12.1

1

1.0

`abort`

18

12

Yes

5

Yes

1.2

≤37

Yes

Yes

Yes

Yes

Yes

`abort_event`

Yes

≤79

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`error_event`

Yes

≤79

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`getAllResponseHeaders`

1

12

4

Starting from Firefox 49, empty headers are returned as empty strings in case the preference `network.http.keep_empty_response_headers_as_empty_string` is set to `true`, defaulting to `false`. Before Firefox 49 empty headers had been ignored. Since Firefox 50 the preference defaults to `true`.

5

Yes

1.2

1

Yes

4

Starting from Firefox 49, empty headers are returned as empty strings in case the preference `network.http.keep_empty_response_headers_as_empty_string` is set to `true`, defaulting to `false`. Before Firefox 49 empty headers had been ignored. Since Firefox 50 the preference defaults to `true`.

Yes

Yes

Yes

`getResponseHeader`

1

12

1

Starting from Firefox 49, empty headers are returned as empty strings in case the preference `network.http.keep_empty_response_headers_as_empty_string` is set to `true`, defaulting to `false`. Before Firefox 49 empty headers had been ignored. Since Firefox 50 the preference defaults to `true`.

5

8

1.2

1

18

4

Starting from Firefox 49, empty headers are returned as empty strings in case the preference `network.http.keep_empty_response_headers_as_empty_string` is set to `true`, defaulting to `false`. Before Firefox 49 empty headers had been ignored. Since Firefox 50 the preference defaults to `true`.

10.1

1

1.0

`load_event`

Yes

≤79

Yes

9

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`loadend_event`

Yes

≤79

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`loadstart_event`

Yes

≤79

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`onreadystatechange`

1

12

1

5

9

1.2

1

18

4

10.1

1

1.0

`open`

1

12

1

Starting in Firefox 30, synchronous requests on the main thread have been deprecated due to their negative impact on performance and the user experience. Therefore, the `async` parameter may not be `false` except in a `Worker`.

5

8

1.2

1

18

4

Starting in Firefox 30, synchronous requests on the main thread have been deprecated due to their negative impact on performance and the user experience. Therefore, the `async` parameter may not be `false` except in a `Worker`.

10.1

1

1.0

`overrideMimeType`

1

12

Yes

11

5

Implemented via `ActiveXObject`

Yes

1.2

1

18

Yes

Yes

Yes

1.0

`progress_event`

Yes

≤79

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`readyState`

1

12

1

7

8

1.2

1

18

4

10.1

1

1.0

`response`

9

12

6

10

11.6

5.1

≤37

18

6

12

6

1.0

`responseText`

1

12

1

5

Before Internet Explorer 10, the value of `XMLHttpRequest.responseText` could be read only once the request was complete.

8

1.2

1

18

4

10.1

1

1.0

`responseType`

31

12

6

10

12-15

18

7

55

55

50

42

7

6.0

`responseURL`

37

14

32

No

24

8

37

37

32

24

Yes

3.0

`responseXML`

Yes

12

Yes

Prior to Firefox 51, an error parsing the received data added a `<parsererror>` node to the top of the `Document` and then returned the `Document` in whatever state it happens to be in. This was inconsistent with the specification. Starting with Firefox 51, this scenario now correctly returns `null` as per the spec.

Yes

Yes

Yes

Yes

Yes

Yes

Prior to Firefox 51, an error parsing the received data added a `<parsererror>` node to the top of the `Document` and then returned the `Document` in whatever state it happens to be in. This was inconsistent with the specification. Starting with Firefox 51, this scenario now correctly returns `null` as per the spec.

Yes

Yes

Yes

`send`

1

12

1

5

8

1.2

1

18

4

10.1

1

1.0

`setRequestHeader`

1

12

1

5

8

1.2

1

18

4

10.1

1

1.0

`status`

1

12

1

7

Internet Explorer version 5 and 6 supported ajax calls using `ActiveXObject()`

8

1.2

1

18

4

10.1

1

1.0

`statusText`

1

12

1

7

Internet Explorer version 5 and 6 supported ajax calls using `ActiveXObject()`

Yes

1.2

1

18

4

Yes

Yes

1.0

`timeout`

29

12

12

8

17

12-16

6.1

≤37

29

14

18

12-16

7

2.0

`timeout_event`

Yes

≤18

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`upload`

1

12

Yes

10

Yes

10

1

18

Yes

Yes

Yes

1.0

`withCredentials`

3

12

3.5

Starting with Firefox 11, it's no longer supported to use the `withCredentials` attribute when performing synchronous requests. Attempting to do so throws an `NS_ERROR_DOM_INVALID_ACCESS_ERR` exception.

10

Internet Explorer versions 8 and 9 supported cross-domain requests (CORS) using [`XDomainRequest`](https://developer.mozilla.org/docs/Web/API/XDomainRequest).

12

4

≤37

18

4

Starting with Firefox 11, it's no longer supported to use the `withCredentials` attribute when performing synchronous requests. Attempting to do so throws an `NS_ERROR_DOM_INVALID_ACCESS_ERR` exception.

12

3.2

1.0

`worker_support`

4

Not supported in service workers.

12

Not supported in service workers.

3.5

Not supported in service workers.

10

Not supported in service workers.

10.6

Not supported in service workers.

4

Not supported in service workers.

4

Not supported in service workers.

18

Not supported in service workers.

4

Not supported in service workers.

11

Not supported in service workers.

5.1

Not supported in service workers.

1.0

Not supported in service workers.

See also
--------

-   [`XMLSerializer`](xmlserializer): Serializing a DOM tree into XML
-   MDN tutorials covering `XMLHttpRequest`:
    -   [Ajax — Getting Started](https://developer.mozilla.org/en-US/docs/Web/Guide/AJAX/Getting_Started)
    -   [Using XMLHttpRequest](xmlhttprequest/using_xmlhttprequest)
    -   [HTML in XMLHttpRequest](xmlhttprequest/html_in_xmlhttprequest)
    -   [Fetch API](fetch_api)
-   [HTML5 Rocks — New Tricks in XMLHttpRequest2](https://www.html5rocks.com/en/tutorials/file/xhr2/)
-   Feature-Policy directive [`sync-xhr`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/sync-xhr)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest</a>
