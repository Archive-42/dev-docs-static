# Attr.localName

The `Attr.localName` read-only property returns the local part of the qualified name of an attribute.

## Syntax

    name = attribute.localName

### Return value

A [`DOMString`](../domstring) representing the local part of the attribute's qualified name.

## Example

The following example shows "id" in an alert dialog.

### HTML Content

    <button id="example">Click me</button>

### JavaScript Content

    const element = document.querySelector("#example");
    element.addEventListener("click", function() {
      const attribute = element.attributes[0];
      alert(attribute.localName);
    });

## Notes

The local name of an attribute is the part of the attribute's qualified name that comes after the colon. Qualified names are typically used in XML as part of the namespace(s) of the particular XML documents.

**Note:** In Gecko 1.9.2 and earlier, the property returns the upper-cased version of the local name for HTML attributes in HTML DOMs (as opposed to XHTML attributes in XML DOMs). In later versions, in compliance with HTML5, the property returns in the case of the internal DOM storage, which is lower case for both HTML attributes in HTML DOMs and XHTML attributes in XML DOMs.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-attr-localname">DOM<br />
<span class="small">The definition of 'Attr.localName' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

## See also

- [`Attr.namespaceURI`](namespaceuri)
- [`Attr.prefix`](prefix)
- [`Element.localName`](../element/localname)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Attr/localName" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Attr/localName</a>
