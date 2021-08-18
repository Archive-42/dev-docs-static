Element.tagName
===============

The `tagName` read-only property of the [`Element`](../element) interface returns the tag name of the element on which it's called. For example, if the element is an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img), its `tagName` property is `"IMG"` (for HTML documents; it may be cased differently for XML/XHTML documents).

Syntax
------

    elementName = Element.tagName;

### Value

A string indicating the element's tag name. This string's capitalization depends on the document type:

-   For DOM trees which represent HTML documents, the returned tag name is always in the canonical upper-case form. For example, `tagName` called on a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) element returns `"DIV"`.
-   The tag names of elements in an XML DOM tree are returned in the same case in which they're written in the original XML file. If an XML document includes a tag `"<SomeTag>"`, then the `tagName` property's value is `"SomeTag"`.

For [`Element`](../element) objects, the value of `tagName` is the same as the value of the [`nodeName`](../node/nodename) property the element object inherits from [`Node`](../node).

Example
-------

### HTML

    <span id="born">When I was born...</span>

### JavaScript

    var span = document.getElementById("born");
    console.log(span.tagName);

In XHTML (or any other XML format), the original case will be maintained, so `"span"` would be output in case the original tag name was created lowercase. In HTML, `"SPAN"` would be output instead regardless of the case used while creating the original document.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-tagname">DOM<br />
<span class="small">The definition of 'Element: tagName' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`tagName`

1

12

1

5

8

1

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/tagName" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/tagName</a>
