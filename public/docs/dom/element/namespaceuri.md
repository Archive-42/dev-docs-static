# Element.namespaceURI

The `Element.namespaceURI` read-only property returns the namespace URI of the element, or `null` if the element is not in a namespace.

## Syntax

    namespace = element.namespaceURI

## Example

In this snippet, an element is being examined for its <span class="page-not-created">`localName`</span> and its `namespaceURI`. If the `namespaceURI` returns the XUL namespace and the `localName` returns "browser", then the node is understood to be a XUL `<browser/>`.

    if (element.localName == "browser" &&
        element.namespaceURI == "http://www.mozilla.org/keymaster/gatekeeper/there.is.only.xul") {
      // this is a XUL browser
    }

## Notes

This is not a computed value that is the result of a namespace lookup based on an examination of the namespace declarations in scope. The namespace URI of a node is frozen at the node creation time.

In Firefox 3.5 and earlier, the namespace URI for HTML elements in HTML documents is `null`. In later versions, in compliance with HTML5, it is `http://www.w3.org/1999/xhtml` as in XHTML.

You can create an element with the specified `namespaceURI` using the DOM Level 2 method [document.createElementNS](../document/createelementns).

The DOM does not handle or enforce namespace validation per se. It is up to the DOM application to do any validation necessary. Also note that the namespace prefix, once it is associated with a particular element, cannot be changed.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-element-namespaceuri">DOM<br />
<span class="small">The definition of 'Element: namespaceURI' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

9

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- [`Element.localName`](localname)
- [`Element.prefix`](prefix)
- [`Attr.namespaceURI`](../attr/namespaceuri)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/namespaceURI" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/namespaceURI</a>
