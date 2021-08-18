XMLHttpRequest.overrideMimeType()
=================================

**Draft**

This page is not complete.

The [`XMLHttpRequest`](../xmlhttprequest) method `overrideMimeType()` specifies a MIME type other than the one provided by the server to be used instead when interpreting the data being transferred in a request. This may be used, for example, to force a stream to be treated and parsed as `"text/xml"`, even if the server does not report it as such. This method must be called before calling [`send()`](send).

Syntax
------

    XMLHttpRequest.overrideMimeType(mimeType)

### Parameters

`mimeType`  
A [`DOMString`](../domstring) specifying the MIME type to use instead of the one specified by the server. If the server doesn't specify a type, `XMLHttpRequest` assumes `"text/xml"`.

### Return value

`undefined`.

Example
-------

This example specifies a MIME type of `"text/plain"`, overriding the server's stated type for the data being received.

**Note:** If the server doesn't provide a `Content-Type` header, [`XMLHttpRequest`](../xmlhttprequest) assumes that the MIME type is `"text/xml"`. If the content isn't valid XML, an "XML Parsing Error: not well-formed" error occurs. You can avoid this by calling `overrideMimeType()` to specify a different type.

    // Interpret the received data as plain text

    req = new XMLHttpRequest();
    req.overrideMimeType("text/plain");
    req.addEventListener("load", callback, false);
    req.open("get", url);
    req.send();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#the-overridemimetype()-method">XMLHttpRequest<br />
<span class="small">The definition of 'overrideMimeType()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

See also
--------

-   [Using XMLHttpRequest](using_xmlhttprequest)
-   [`XMLHttpRequest.responseType`](responsetype)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/overrideMimeType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/overrideMimeType</a>
