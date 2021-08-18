# Attr

The `Attr` interface represents one of a DOM element's attributes as an object. In most DOM methods, you will directly retrieve the attribute as a string (e.g., [`Element.getAttribute()`](element/getattribute)), but certain functions (e.g., [`Element.getAttributeNode()`](element/getattributenode)) or means of iterating return `Attr` types.

**Warning:** Starting in Gecko 7.0 (Firefox 7.0 / Thunderbird 7.0 / SeaMonkey 2.4), a number of deprecated properties and methods output warning messages to the console. You should revise your code accordingly. See [Deprecated properties and methods](#deprecated_properties_and_methods) for a complete list.

## Properties

<span class="page-not-created">`name`</span> <span class="badge inline readonly">Read only </span>  
The attribute's name.

[`namespaceURI`](attr/namespaceuri) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) representing the namespace URI of the attribute, or `null` if there is no namespace.

[`localName`](attr/localname) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) representing the local part of the qualified name of the attribute.

[`prefix`](attr/prefix) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) representing the namespace prefix of the attribute, or `null` if no prefix is specified.

<span class="page-not-created">`ownerElement`</span> <span class="badge inline readonly">Read only </span>  
The element holding the attribute.

**Note:** DOM Level 4 removed this property. The assumption was that since you get an `Attr` object from an [`Element`](element), you should already know the associated element.  
As that doesn't hold true in cases like `Attr` objects being returned by [`Document.evaluate`](document/evaluate), the DOM Living Standard reintroduced the property.

Gecko outputs a deprecation note starting from Gecko 7.0 (Firefox 7.0 / Thunderbird 7.0 / SeaMonkey 2.4). This note was removed again in Gecko 49.0 (Firefox 49.0 / Thunderbird 49.0 / SeaMonkey 2.46).

<span class="page-not-created">`specified`</span> <span class="badge inline readonly">Read only </span>  
This property always returns `true`. Originally, it returned `true `if the attribute was explicitly specified in the source code or by a script, and `false` if its value came from the default one defined in the document's DTD.

<span class="page-not-created">`value`</span>  
The attribute's value.

## Deprecated properties and methods

The following properties have been deprecated. Where available, the appropriate replacement is noted.

`attributes`  
This property now always returns `NULL`.

`childNodes` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
This property now always returns an empty [`NodeList`](nodelist).

`firstChild` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
This property now always returns `NULL`.

`isId` <span class="badge inline readonly">Read only </span>  
Indicates whether the attribute is an "ID attribute". An "ID attribute" being an attribute which value is expected to be unique across a DOM Document. In HTML DOM, "id" is the only ID attribute, but XML documents could define others. Whether or not an attribute is unique is often determined by a [DTD](https://developer.mozilla.org/en-US/docs/Glossary/Doctype) or other schema description.

`lastChild` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
This property now always returns `NULL`.

`nextSibling`  
This property now always returns `NULL`.

`nodeName`  
Use <span class="page-not-created">`Attr.name`</span> instead.

`nodeType`  
This property now always returns 2 (`ATTRIBUTE_NODE`).

`nodeValue`  
Use <span class="page-not-created">`Attr.value`</span> instead.

`ownerDocument`  
You shouldn't have been using this in the first place, so you probably don't care that this is going away.

`parentNode`  
This property now always returns `NULL`.

`previousSibling`  
This property now always returns `NULL`.

`schemaTypeInfo` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline readonly">Read only </span>  
The type information associated with this attribute. While the type information contained in this attribute is guaranteed to be correct after loading the document or invoking <span class="page-not-created">`Document.normalizeDocument`</span>, this property may not be reliable if the node was moved.

`specified`  
This property now always returns `true`.

`textContent`  
Use <span class="page-not-created">`Attr.value`</span> instead.

The following methods have been deprecated:

`appendChild()` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Modify the value of <span class="page-not-created">`Attr.value`</span> instead.

`cloneNode()`  
You shouldn't have been using this in the first place, so you probably don't care that this is going away.

`createAttribute()`  
Use [`Element.setAttribute()`](element/setattribute) instead.

`createAttributeNS()`  
Use [`Element.setAttributeNS()`](element/setattributens) instead.

`getAttributeNode()`  
Use [`Element.getAttribute()`](element/getattribute) instead.

`getAttributeNodeNS()`  
Use [`Element.getAttributeNS()`](element/getattributens) instead.

`hasAttributes()` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
This method now always returns false.

`hasChildNodes()`  
This method now always returns false.

`insertBefore()`  
Modify the value of <span class="page-not-created">`Attr.value`</span> instead.

`isSupported()`  
You shouldn't have been using this in the first place, so you probably don't care that this is going away.

`isEqualNode()`  
You shouldn't have been using this in the first place, so you probably don't care that this is going away.

`normalize()`  
You shouldn't have been using this in the first place, so you probably don't care that this is going away.

`removeAttributeNode()`  
Use [`Element.removeAttribute()`](element/removeattribute) instead.

`removeChild()` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Modify the value of <span class="page-not-created">`Attr.value`</span> instead.

`replaceChild()` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Modify the value of <span class="page-not-created">`Attr.value`</span> instead.

`setAttributeNode()`  
Use [`Element.setAttribute()`](element/setattribute) instead.

`setAttributeNodeNS()`  
Use [`Element.setAttributeNS()`](element/setattributens) instead.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-attr">DOM<br />
<span class="small">The definition of 'Attr' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added <code>ownerElement</code> property back</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/dom/#interface-attr">DOM4<br />
<span class="small">The definition of 'Attr' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Moved <code>namespaceURI</code>, <code>prefix</code> and <code>localName</code> from <a href="node"><code>Node</code></a> to this API and removed <code>ownerElement</code>, <code>schemaTypeInfo</code> and <code>isId</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-637646024">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Attr' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

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

`Attr`

1

12

1

5.5

8

1

1

18

4

10.1

1

1.0

`localName`

1

12

1

No

≤12.1

1

1

18

4

≤12.1

1

1.0

`name`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

`namespaceURI`

1

12

1

No

≤12.1

1

1

18

4

≤12.1

1

1.0

`ownerElement`

1

12

1

8

≤12.1

1

1

18

4

≤12.1

1

1.0

`prefix`

1

12

1

No

≤12.1

1

1

18

4

≤12.1

1

1.0

`specified`

1

12

1

5.5

≤12.1

1

1

18

4

≤12.1

1

1.0

`value`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Attr" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Attr</a>
