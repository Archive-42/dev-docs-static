XMLHttpRequest.response
=======================

The [`XMLHttpRequest`](../xmlhttprequest) `response` property returns the response's body content as an [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer), [`Blob`](../blob), [`Document`](../document), JavaScript [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object), or [`DOMString`](../domstring), depending on the value of the request's [`responseType`](responsetype) property.

Syntax
------

    var body = XMLHttpRequest.response;

### Value

An appropriate object based on the value of [`responseType`](responsetype). You may attempt to request the data be provided in a specific format by setting the value of `responseType` after calling [`open()`](open) to initialize the request but before calling [`send()`](send) to send the request to the server.

The value is `null` if the request is not yet complete or was unsuccessful, with the exception that when reading text data using a `responseType` of `"text"` or the empty string (`""`), the response can contain the response so far while the request is still in the `LOADING` [`readyState`](readystate) (3).

The response types are described below.

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

Example
-------

This example presents a function, `load()`, which loads and processes a page from the server. It works by creating an [`XMLHttpRequest`](../xmlhttprequest) object and creating a listener for `readystatechange` events such that when `readyState` changes to `DONE` (4), the `response` is obtained and passed into the callback function provided to `load()`.

The content is handled as raw text data (since nothing here is overriding the default [`responseType`](responsetype)).

    var url = 'somePage.html'; //A local page

    function load(url, callback) {
      var xhr = new XMLHttpRequest();

      xhr.onreadystatechange = function() {
        if (xhr.readyState === 4) {
          callback(xhr.response);
        }
      }

      xhr.open('GET', url, true);
      xhr.send('');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#the-response-attribute">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

See also
--------

-   [Using XMLHttpRequest](using_xmlhttprequest)
-   Getting text and HTML/XML data: [`XMLHttpRequest.responseText`](responsetext) and [`XMLHttpRequest.responseXML`](responsexml)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/response" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/response</a>
