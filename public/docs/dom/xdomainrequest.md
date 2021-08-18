XDomainRequest
==============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

XDomainRequest is an implementation of [HTTP access control (CORS)](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) that worked in Internet Explorer 8 and 9. It was removed in Internet Explorer 10 in favor of using [XMLHttpRequest](xmlhttprequest) with proper CORS; if you are targeting Internet Explorer 10 or later, or wish to support any other browser, you need to use standard [HTTP access control](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS).

This interface can send both GET and POST requests.

Syntax
------

    var xdr = new XDomainRequest();

Returns a new `XDomainRequest` object, which can then be used to make and manage these requests.

Properties
----------

[`XDomainRequest.timeout`](xdomainrequest/timeout)  
Gets or sets the amount of time until a request times out.

[`XDomainRequest.responseText`](xdomainrequest/responsetext)  
Gets the response body as a string.

Methods
-------

[`XDomainRequest.open()`](xdomainrequest/open)  
Opens the request, specifying the method (GET/POST) and URL.

[`XDomainRequest.send()`](xdomainrequest/send)  
Sends the request. POST data is specified in this method.

[`XDomainRequest.abort()`](xdomainrequest/abort)  
Aborts the request.

Event handlers
--------------

[`XDomainRequest.onprogress`](xdomainrequest/onprogress)  
A handler for when the request has made progress between the send method call and the onload event.

[`XDomainRequest.ontimeout`](xdomainrequest/ontimeout)  
A handler for when the request times out.

[`XDomainRequest.onerror`](xdomainrequest/onerror)  
A handler for when a request has errored.

[`XDomainRequest.onload`](xdomainrequest/onload)  
A handler for when the full response has been received from the server.

Example
-------

    if(window.XDomainRequest){
      var xdr = new XDomainRequest();

      xdr.open("get", "http://example.com/api/method");

      xdr.onprogress = function () {
        //Progress
      };

      xdr.ontimeout = function () {
        //Timeout
      };

      xdr.onerror = function () {
        //Error Occurred
      };

      xdr.onload = function() {
        //success(xdr.responseText);
      }

      setTimeout(function () {
        xdr.send();
      }, 0);
    }

**Note:** The `xdr.send()` call is wrapped in a timeout (see [`window.setTimeout()`](windoworworkerglobalscope/settimeout) to prevent an issue with the interface where some requests are lost if multiple `XDomainRequest`s are being sent at the same time.

**Note:** The `xdr.onprogress` event should always be defined, even as an empty function, or `XDomainRequest` may not fire onload for duplicate requests.

Security
--------

The XDomainRequest is built to be secure in multiple ways.

-   The origin's security protocol must match that of the requested URL. (http to http, https to https). If these do not match, the request will error "Access is Denied".
-   The requested URL's server must have the [`Access-Control-Allow-Origin`](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS#access-control-allow-origin) header set to either all ("\*") or to include the origin of the request.

Specifications
--------------

This interface and its methods are non-standard.

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

`XDomainRequest`

No

No

No

8-11

No

No

No

No

No

No

No

No

`abort`

No

No

No

8-11

No

No

No

No

No

No

No

No

`onerror`

No

No

No

8-11

No

No

No

No

No

No

No

No

`onload`

No

No

No

8-11

No

No

No

No

No

No

No

No

`onprogress`

No

No

No

8-11

No

No

No

No

No

No

No

No

`ontimeout`

No

No

No

8-11

No

No

No

No

No

No

No

No

`open`

No

No

No

8-11

No

No

No

No

No

No

No

No

`responseText`

No

No

No

8-11

No

No

No

No

No

No

No

No

`send`

No

No

No

8-11

No

No

No

No

No

No

No

No

`timeout`

No

No

No

8-11

No

No

No

No

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XDomainRequest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XDomainRequest</a>
