XMLHttpRequestResponseType
==========================

The `XMLHttpRequestResponseType` type is an enumerated set of strings which are used to specify the type of data contained in the [`response`](xmlhttprequest/response) of an [`XMLHttpRequest`](xmlhttprequest). These values are used when getting or setting the [`responseType`](xmlhttprequest/responsetype) on the request.

Values
------

`""`  
An empty `responseType` string is treated the same as `"text"`, the default type.

`arraybuffer`  
The [`response`](xmlhttprequest/response) is a JavaScript [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) containing binary data.

`blob`  
The `response` is a [`Blob`](blob) object containing the binary data.

`document`  
The `response` is an [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) [`Document`](document) or [XML](https://developer.mozilla.org/en-US/docs/Glossary/XML) [`XMLDocument`](xmldocument), as appropriate based on the MIME type of the received data. See [HTML in XMLHttpRequest](xmlhttprequest/html_in_xmlhttprequest) to learn more about using XHR to fetch HTML content.

`json`  
The `response` is a JavaScript object created by parsing the contents of received data as [JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON).

`text`  
The `response` is a text in a [`DOMString`](domstring) object.

 `ms-stream` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
The `response` is part of a streaming download; this response type is only allowed for download requests, and is only supported by Internet Explorer.

Deprecated values
-----------------

 `moz-chunked-arraybuffer` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
A Firefox-only value which instructs `XMLHttpRequest` to deliver [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) objects containing chunks of the incoming data. Accessing `response` during a `progress` event returns the data received so far. Outside the `progress` event handler, the value of `response` is always `null`. You shouldn't use this non-standard (and, as of Firefox 68, entirely removed) API; instead, consider using [the Fetch API with readable streams](streams_api/using_readable_streams#consuming_a_fetch_as_a_stream), which offers a standard alternative to accessing the response in a streaming fashion.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/">XMLHttpRequest</a></td><td><span class="spec-">Unknown</span></td><td>Live standard, latest version</td></tr></tbody></table>

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

`XMLHttpRequestResponseType`

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

-   [Using XMLHttpRequest](xmlhttprequest/using_xmlhttprequest)
-   [HTML in XMLHttpRequest](xmlhttprequest/html_in_xmlhttprequest)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestResponseType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequestResponseType</a>
