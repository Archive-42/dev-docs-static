# Document.createAttribute()

The `Document.createAttribute()` method creates a new attribute node, and returns it. The object created a node implementing the [`Attr`](../attr) interface. The DOM does not enforce what sort of attributes can be added to a particular element in this manner.

The string given in parameter is converted to lowercase.

## Syntax

    attribute = document.createAttribute(name)

### Parameters

- `name` is a string containing the name of the attribute.

### Return value

A [`Attr`](../attr) node.

### Exceptions

- `INVALID_CHARACTER_ERR` if the parameter contains invalid characters for XML attribute.

## Example

    var node = document.getElementById("div1");
    var a = document.createAttribute("my_attrib");
    a.value = "newVal";
    node.setAttributeNode(a);
    console.log(node.getAttribute("my_attrib")); // "newVal"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-createattribute">DOM<br />
<span class="small">The definition of 'Document.createAttribute()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Precised behavior with uppercase characters</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-1084891198">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Document.createAttribute()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-1084891198">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Document.createAttribute()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-1084891198">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Document.createAttribute()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`createAttribute`

1

12

44

1-44

The parameter was not converted to its lowercase variant.

6

≤12.1

1

1

18

44

4-44

The parameter was not converted to its lowercase variant.

≤12.1

1

1.0

## See also

- [`Document.createElement()`](createelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/createAttribute" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/createAttribute</a>
