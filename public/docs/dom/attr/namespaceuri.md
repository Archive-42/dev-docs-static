# Attr.namespaceURI

The `Attr.namespaceURI` read-only property returns the namespace URI of the attribute, or `null` if the element is not in a namespace.

## Syntax

    namespace = attribute.namespaceURI

## Example

In this snippet, an attribute is being examined for its <span class="page-not-created">`localName`</span> and its `namespaceURI`. If the `namespaceURI` returns the XUL namespace and the `localName` returns "browser", then the node is understood to be a XUL `<browser/>`.

    if (attribute.localName == "value" &&
        attribute.namespaceURI == "http://www.mozilla.org/keymaster/gatekeeper/there.is.only.xul") {
      // this is a XUL value
    }

## Notes

This is not a computed value that is the result of a namespace lookup based on an examination of the namespace declarations in scope. The namespace URI of an attribute is frozen at the attribute creation time.

In Firefox 3.5 and earlier, the namespace URI for HTML attributes in HTML documents is `null`. In later versions, in compliance with HTML5, it is `https://www.w3.org/1999/xhtml` as in XHTML.

You can create an attribute with the specified `namespaceURI` using the DOM Level 2 method [`Element.setAttributeNS`](../element/setattributens).

Per the [Namespaces in XML](https://www.w3.org/TR/xml-names11/) specification, an attribute does not inherit its namespace from the element it is attached to. If an attribute is not explicitly given a namespace, it has no namespace.

The DOM does not handle or enforce namespace validation per se. It is up to the DOM application to do any validation necessary. Note too that the namespace prefix, once it is associated with a particular node, cannot be changed.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-attr-namespaceuri">DOM<br />
<span class="small">The definition of 'Attr: namespaceURI' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

## See also

- [`Attr.localName`](localname)
- [`Attr.prefix`](prefix)
- [`Element.namespaceURI`](../element/namespaceuri)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Attr/namespaceURI" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Attr/namespaceURI</a>
