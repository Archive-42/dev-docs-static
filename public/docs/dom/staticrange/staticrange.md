StaticRange.StaticRange()
=========================

The `StaticRange()` constructor creates a new [`StaticRange`](../staticrange) object representing a span of content within the DOM. It includes properties identifying the standard and end positions of the range as well as a Boolean indicating whether or not the range is **collapsed** (that is, empty).

Syntax
------

    var staticRange = new StaticRange(rangeSpec)

### Parameters

`rangeSpec`  
The required `rangeSpec` parameter is an object adhering to the <span class="page-not-created">`StaticRangeInit`</span> dictionary. The four required `rangeSpec` properties are:

`startContainer`  
The [`Node`](../node) in which the starting point of the range is located.

`startOffset`  
The offset into the starting node at which the first character of the range is found.

`endContainer`  
The `Node` in which the end point of the range is located.

`endOffset`  
The offset into the node indicated by `endOffset` at which the last character in the range is located.

### Return value

A new `StaticRange` object initialized with the values given in the `rangeSpec` object.

### Exceptions

`InvalidNodeTypeError`  
A [`DOMException`](../domexception) fired if either or both of the `startContainer` and/or `endContainer` are a type of node which you can't include in a range. Those node types are `Node.DOCUMENT_TYPE_NODE` (representing the [`DocumentType`](../documenttype) node derived from the [DTD](https://developer.mozilla.org/en-US/docs/Glossary/Doctype) identified using the `doctype` preamble in the HTML, for example) and the [`Attr`](../attr) node describing an attribute of an element on the DOM..

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-staticrange-staticrange">DOM<br />
<span class="small">The definition of 'StaticRange()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`StaticRange`

No

No

71

No

No

13.1

No

No

No

No

13.4

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StaticRange/StaticRange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StaticRange/StaticRange</a>
