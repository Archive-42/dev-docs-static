XDomainRequest.send()
=====================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Sends an [`XDomainRequest`](../xdomainrequest) which has previously been opened calling [`XDomainRequest.open()`](open).

Syntax
------

    xdr.send(data);

Parameters
----------

`data`  
The form data to be sent with the request. This parameter is optional for GET requests.

Example
-------

    var xdr = new XDomainRequest();
    xdr.open("POST", "http://example.com/api/method");
    xdr.onload = function(){
      //Handle Response with xdr.responseText
    }
    xdr.send("param1=value1&param2=value2");

Specifications
--------------

Not part of any specification.

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XDomainRequest/send" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XDomainRequest/send</a>
