# Document.firstElementChild

The `Document.firstElementChild` read-only property returns the document's first child [`Element`](../element), or `null` if there are no child elements.

For HTML documents, this is usually the only child, the root `<html>` element.

See [`Element.firstElementChild`](../element/firstelementchild) for the first child element of specific elements within a document.

## Syntax

    // Getter
    element = document.firstElementChild;

    // No setter; read-only property

## Example

    document.firstElementChild;
    // returns the root <html> element, the only child of the document

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-parentnode-firstelementchild">DOM<br />
<span class="small">The definition of 'ParentNode.firstElementChild' in that specification.</span></a></td></tr></tbody></table>

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

`firstElementChild`

29

17

25

No

16

9

≤37

29

25

16

9

2.0

## See also

- [`Element.firstElementChild`](../element/firstelementchild)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/firstElementChild" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/firstElementChild</a>
