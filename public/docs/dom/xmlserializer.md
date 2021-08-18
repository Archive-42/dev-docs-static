XMLSerializer
=============

The `XMLSerializer` interface provides the [`serializeToString()`](xmlserializer/serializetostring) method to construct an XML string representing a [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) tree.

Methods
-------

[`serializeToString()`](xmlserializer/serializetostring)  
Returns the serialized subtree of a string.

 <span class="page-not-created">`serializeToStream()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The subtree rooted by the specified element is serialized to a byte stream using the character set specified.

Examples
--------

### Serializing XML into a string

The first, basic, example just serializes an entire document into a string containing XML.

     var s = new XMLSerializer();
     var d = document;
     var str = s.serializeToString(d);
     saveXML(str);

This involves creating a new `XMLSerializer` object, then passing the [`Document`](document) to be serialized into [`serializeToString()`](xmlserializer/serializetostring), which returns the XML equivalent of the document.

### Inserting nodes into a DOM based on XML

This example uses the [`Element.insertAdjacentHTML()`](element/insertadjacenthtml) method to insert a new DOM [`Node`](node) into the body of the [`Document`](document), based on XML created by serializing an [`Element`](element) object.

**Note:** In the real world, you should usually instead call [`importNode()`](document/importnode) method to import the new node into the DOM, then call one of the following methods to add the node to the DOM tree:

-   The [`Element.append()`](element/append)/[`Element.prepend()`](element/prepend) and [`Document.append()`](document/append)/[`Document.prepend()`](document/prepend) methods.
-   The [`Node.replaceWith()`](childnode/replacewith) method (to replace an existing node with the new one)
-   The <span class="page-not-created">`Document.insertAdjacentElement()`</span> and [`Element.insertAdjacentElement()`](element/insertadjacentelement) methods.

Because `insertAdjacentHTML()` accepts a string and not a `Node` as its second parameter, `XMLSerializer` is used to first convert the node into a string.

    var inp = document.createElement('input');
    var XMLS = new XMLSerializer();
    var inp_xmls = XMLS.serializeToString(inp); // First convert DOM node into a string

    // Insert the newly created node into the document's body
    document.body.insertAdjacentHTML('afterbegin', inp_xmls);

The code creates a new [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) element by calling [`Document.createElement()`](document/createelement), then serializes it into XML using [`serializeToString()`](xmlserializer/serializetostring).

Once that's done, `insertAdjacentHTML()` is used to insert the `<input>` element into the DOM.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/DOM-Parsing/#the-xmlserializer-interface">DOM Parsing and Serialization<br />
<span class="small">The definition of 'XMLSerializer' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`XMLSerializer`

Yes

12

Yes

9

Yes

3

Yes

Yes

Yes

Yes

Yes

Yes

`XMLSerializer`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`serializeToStream`

Yes

79

Yes-20

No

Yes

No

Yes

Yes

Yes-20

Yes

No

Yes

`serializeToString`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

See also
--------

-   [Parsing and serializing XML](https://developer.mozilla.org/en-US/docs/Web/Guide/Parsing_and_serializing_XML)
-   [`XMLHttpRequest`](xmlhttprequest)
-   [`DOMParser`](domparser)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLSerializer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLSerializer</a>
