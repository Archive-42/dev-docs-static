XDomainRequest.responseText
===========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Returns the response body of an [`XDomainRequest`](../xdomainrequest) as a string.

**Note:** This property is valid during the [`XDomainRequest.onprogress`](onprogress) and [`XDomainRequest.onload`](onload) events.

Syntax
------

    var response = xdr.responseText;

This sets `response` to contain the response body of the request, as a string.

Example
-------

    var response = xdr.responseText;

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XDomainRequest/responseText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XDomainRequest/responseText</a>
