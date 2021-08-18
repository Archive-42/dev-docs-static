XMLHttpRequest.responseXML
==========================

The `XMLHttpRequest.responseXML` read-only property returns a [`Document`](../document) containing the HTML or XML retrieved by the request; or `null` if the request was unsuccessful, has not yet been sent, or if the data can't be parsed as XML or HTML.

**Note:** The name `responseXML` is an artifact of this property's history; it works for both HTML and XML.

Usually, the response is parsed as "`text/xml`". If the [`responseType`](responsetype) is set to "`document`" and the request was made asynchronously, instead the response is parsed as "`text/html`". `responseXML` is `null` for any other types of data, as well as for [`data:` URLs](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Data_URIs).

If the server doesn't specify the [`Content-Type`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type) as "`text/xml`" or "`application/xml`", you can use [`XMLHttpRequest.overrideMimeType()`](overridemimetype) to parse it as XML anyway.

This property isn't available to workers.

Syntax
------

    var data = XMLHttpRequest.responseXML;

### Value

A [`Document`](../document) from parsing the XML or HTML received using [`XMLHttpRequest`](../xmlhttprequest), or `null` if no data was received or if the data is not XML/HTML.

### Exceptions

`InvalidStateError`  
The [`responseType`](responsetype) isn't either "`document`" or an empty string.

Example
-------

    var xhr = new XMLHttpRequest;
    xhr.open('GET', '/server');

    // If specified, responseType must be empty string or "document"
    xhr.responseType = 'document';

    // Force the response to be parsed as XML
    xhr.overrideMimeType('text/xml');

    xhr.onload = function () {
      if (xhr.readyState === xhr.DONE && xhr.status === 200) {
        console.log(xhr.response, xhr.responseXML);
      }
    };

    xhr.send();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#the-responsexml-attribute">XMLHttpRequest<br />
<span class="small">The definition of 'responseXML' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

See also
--------

-   [`XMLHttpRequest`](../xmlhttprequest)
-   [`XMLHttpRequest.response`](response)
-   [`XMLHttpRequest.responseType`](responsetype)
-   [Parsing and serializing XML](https://developer.mozilla.org/en-US/docs/Web/Guide/Parsing_and_serializing_XML)
-   Parsing XML into a DOM tree: [`DOMParser`](../domparser)
-   Serializing a DOM tree into XML: [`XMLSerializer`](../xmlserializer) (specifically, the [`serializeToString()`](../xmlserializer/serializetostring) method)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseXML" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/responseXML</a>
