# Document.lastElementChild

The `Document.lastElementChild` read-only property returns the document's last child [`Element`](../element), or `null` if there are no child elements.

For HTML documents, this is usually the only child, the root `<html>` element.

See [`Element.lastElementChild`](../element/lastelementchild) for the last child element of specific elements within a document.

## Syntax

    // Getter
    element = document.lastElementChild;

    // No setter; read-only property

## Example

    document.lastElementChild;
    // returns the root <html> element, the only child of the document

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-parentnode-lastelementchild">DOM<br />
<span class="small">The definition of 'ParentNode.lastElementChild' in that specification.</span></a></td></tr></tbody></table>

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

`lastElementChild`

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

- [`Element.lastElementChild`](../element/lastelementchild)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/lastElementChild" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/lastElementChild</a>
