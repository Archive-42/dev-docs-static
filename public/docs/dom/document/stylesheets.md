# Document.styleSheets

The `styleSheets` read-only property of the [`Document`](../document) interface returns a [`StyleSheetList`](../stylesheetlist) of [`CSSStyleSheet`](../cssstylesheet) objects, for stylesheets explicitly linked into or embedded in a document.

## Syntax

    document.styleSheets

### Value

The returned list is ordered as follows:

- StyleSheets retrieved from [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) headers are placed first, sorted in header order.
- StyleSheets retrieved from the DOM are placed after, sorted in [tree order](https://dom.spec.whatwg.org/#concept-tree-order).

## Examples

    function getStyleSheet(unique_title) {
      for (var i=0; i<document.styleSheets.length; i++) {
        var sheet = document.styleSheets[i];
        if (sheet.title == unique_title) {
          return sheet;
        }
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#extensions-to-the-document-or-shadow-root-interface">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'DocumentOrShadowRoot.styleSheets' in that specification.</span></a></td></tr></tbody></table>

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

`styleSheets`

1

12

1

4

≤12.1

4

1

18

4

≤12.1

3.2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheets" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheets</a>
