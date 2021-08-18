# Document.vlinkColor

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `Document.vlinkColor` property gets/sets the color of links that the user has visited in the document.

## Syntax

    color = document.vlinkColor
    document.vlinkColor = color

### Parameters

- `color` is a string representing the color as a word (e.g., `"red"`) or hexadecimal value (e.g., `"#ff0000"`).

## Notes

- The default value for this property in Mozilla Firefox is purple (`#551a8b` in hexadecimal).
- `Document.vlinkColor` is [deprecated in DOM Level 2 HTML](https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-26809268).
- The recommended alternative is to get/set the color of the CSS [`:visited`](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited) pseudo-class on HTML [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) elements (e.g., `a:visited {color:red;}`).
- Another alternative is `document.body.vLink`, although this is [deprecated in HTML 4.01](https://www.w3.org/TR/html401/struct/global.html#adef-vlink) in favor of the CSS alternative.

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

`vlinkColor`

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

12

1

4

51

≤12.1-51

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

1-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

64

18-64

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

4

47

≤12.1-47

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

11

1-11

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

9.0

1.0-9.0

Only supported for [`HTMLDocument`](https://developer.mozilla.org/docs/Web/API/HTMLDocument), not all `Document` objects.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/vlinkColor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/vlinkColor</a>
