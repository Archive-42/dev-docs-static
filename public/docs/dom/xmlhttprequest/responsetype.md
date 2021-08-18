XMLHttpRequest.responseType
===========================

The [`XMLHttpRequest`](../xmlhttprequest) property `responseType` is an enumerated string value specifying the type of data contained in the response. It also lets the author change the response type. If an empty string is set as the value of `responseType`, the default value of `text` is used.

Syntax
------

    var type = XMLHttpRequest.responseType;

    XMLHttpRequest.responseType = type;

### Value

A string taken from the [`XMLHttpRequestResponseType`](../xmlhttprequestresponsetype) enum which specifies what type of data the response contains.

When setting `responseType` to a particular value, the author should make sure that the server is actually sending a response compatible with that format. If the server returns data that is not compatible with the `responseType` that was set, the value of [`response`](response) will be `null`.

The values supported by `responseType` are the following:

`""`  
An empty `responseType` string is treated the same as `"text"`, the default type.

`arraybuffer`  
The [`response`](response) is a JavaScript [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing binary data.

`blob`  
The `response` is a [`Blob`](../blob) object containing the binary data.

`document`  
The `response` is an [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) [`Document`](../document) or [XML](https://developer.mozilla.org/en-US/docs/Glossary/XML) [`XMLDocument`](../xmldocument), as appropriate based on the MIME type of the received data. See [HTML in XMLHttpRequest](html_in_xmlhttprequest) to learn more about using XHR to fetch HTML content.

`json`  
The `response` is a JavaScript object created by parsing the contents of received data as [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON).

`text`  
The `response` is a text in a [`DOMString`](../domstring) object.

 `ms-stream` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
The `response` is part of a streaming download; this response type is only allowed for download requests, and is only supported by Internet Explorer.

### Exceptions

`InvalidAccessError`  
An attempt was made to change the value of `responseType` on an`XMLHttpRequest` which is in synchronous mode but not in a [`Worker`](../worker). For additional details, see [Synchronous XHR restrictions](#synchronous_xhr%0A____restrictions) below.

Usage notes
-----------

### Synchronous XHR restrictions

You cannot change the value of `responseType` in a synchronous `XMLHttpRequest` except when the request belongs to a [`Worker`](../worker). This restriction is designed in part to help ensure that synchronous operations aren't used for large transactions that block the browser's main thread, thereby bogging down the user experience.

`XMLHttpRequest`s are asynchronous by default; they are only placed in synchronous mode by passing `false` as the value of the optional `async` parameter when calling [`open()`](open).

### Restrictions in Workers

Attempts to set the value of `responseType` to `document` are ignored in a [`Worker`](../worker).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#the-responsetype-attribute">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`arraybuffer`

31

12

6

10

12-15

18

Yes

55

Yes

50

Yes

?

Yes

`blob`

31

12

6

10

18

Yes

55

Yes

50

Yes

?

Yes

`document`

31

12

11

10

No

7

55

Yes

50

Yes

?

Yes

`json`

31

79

10

No

12-15

18

7

55

Yes

50

?

?

Yes

`moz-blob`

No

No

12-58

No

No

No

No

No

No

No

No

No

`moz-chunked-arraybuffer`

No

No

14-68

No

No

No

No

No

50-68

No

No

No

See also
--------

-   [Using XMLHttpRequest](using_xmlhttprequest)
-   [HTML in XMLHttpRequest](html_in_xmlhttprequest)
-   The response data: [`response`](response), [`responseText`](responsetext), and [`responseXML`](responsexml)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseType</a>
