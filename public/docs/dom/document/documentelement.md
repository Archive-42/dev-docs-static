# Document.documentElement

`Document.documentElement` returns the [`Element`](../element) that is the root element of the [`document`](../document) (for example, the [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element for HTML documents).

## Syntax

    const element = document.documentElement

## Example

    const rootElement = document.documentElement;
    const firstTier = rootElement.childNodes;
    // firstTier is a NodeList of the direct children of the root element
    // such as <head> and <body>

    for (const child of firstTier) {
       // do something with each direct child of the root element
    }

## Notes

For any non-empty HTML document, `documentElement` will always be an [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element. For any non-empty XML document, `documentElement` will always be whatever element is the root element of the document.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-document-documentelement">DOM<br />
<span class="small">The definition of 'Document.documentElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`documentElement`

1

12

1

5

7

1

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/documentElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/documentElement</a>
