XMLSerializer.serializeToString()
=================================

The [`XMLSerializer`](../xmlserializer) method `serializeToString()` constructs a string representing the specified [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) tree in [XML](https://developer.mozilla.org/en-US/docs/Glossary/XML) form.

Syntax
------

    xmlString = anXMLSerializer.serializeToString(rootNode);

### Parameters

`rootNode`  
The [`Node`](../node) to use as the root of the DOM tree or subtree for which to construct an XML representation.

### Return value

A [`DOMString`](../domstring) containing the XML representation of the specified DOM tree.

### Exceptions

`TypeError`  
The specified `rootNode` is not a compatible node type. The root node must be either [`Node`](../node) or [`Attr`](../attr).

`InvalidStateError`  
The tree could not be successfully serialized, probably due to issues with the content's compatibility with XML serialization.

`SyntaxError`  
A serialization of HTML was requested but could not succeed due to the content not being well-formed.

Usage notes
-----------

### Compatible node types

The specified root node—and all of its descendants—must be compatible with the XML serialization algorithm. The root node itself must be either a [`Node`](../node) or [`Attr`](../attr) object.

The following types are also permitted as descendants of the root node, in addition to `Node` and `Attr`:

-   [`DocumentType`](../documenttype)
-   [`Document`](../document)
-   [`DocumentFragment`](../documentfragment)
-   [`Element`](../element)
-   [`Comment`](../comment)
-   [`Text`](../text)
-   [`ProcessingInstruction`](../processinginstruction)
-   [`Attr`](../attr)

If any other type is encountered, a `TypeError` exception is thrown.

### Notes on the resulting XML

There are some things worth noting about the XML output by `serializeToString()`:

-   For XML serializations, `Element` and `Attr` nodes are always serialized with their [`namespaceURI`](../element/namespaceuri) intact. This may mean that a previously-specified [`prefix`](../element/prefix) or default namespace may be dropped or altered.
-   The resulting XML is compatible with the HTML parser.
-   Elements in the HTML namespace that have no child nodes (thereby representing empty tags) are serialized with both begin and end tags (`"<someelement></someelement>"`) instead of using the empty-element tag (`"<someelement/>"`).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/DOM-Parsing/#dom-xmlserializer-serializetostring">DOM Parsing and Serialization<br />
<span class="small">The definition of 'serializeToString()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

-   [Parsing and serializing XML](https://developer.mozilla.org/en-US/docs/Web/Guide/Parsing_and_serializing_XML)
-   Serializing to HTML: [`Element.innerHTML`](../element/innerhtml) and [`Element.outerHTML`](../element/outerhtml)
-   Parsing HTML or XML to create a DOM tree: [`DOMParser`](../domparser)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLSerializer/serializeToString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLSerializer/serializeToString</a>
