# Document.alinkColor

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Returns or sets the color of an active link in the document body. A link is active during the time between `mousedown` and `mouseup` events.

## Syntax

    var color = document.alinkColor;
    document.alinkColor = color;

color is a string containing the name of the color (e.g., `blue`, `darkblue`, etc.) or the hexadecimal value of the color (e.g., `#0000FF`)

## Notes

The default value for this property in Mozilla Firefox is red (`#ee0000` in hexadecimal).

`document.alinkColor` is deprecated in [DOM Level 2 HTML](https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-26809268). One alternative is the CSS selector [`:active`](https://developer.mozilla.org/en-US/docs/Web/CSS/:active).

Another alternative is `document.body.aLink`, although this is [deprecated in HTML 4.01](https://www.w3.org/TR/html401/struct/global.html#adef-alink) in favor of the CSS alternative.

[Gecko](https://developer.mozilla.org/en-US/docs/Mozilla/Gecko) supports both `alinkColor`/`:active` and [`:focus`](https://developer.mozilla.org/en-US/docs/Web/CSS/:focus). Internet Explorer 6 and 7 support `alinkColor`/`:active` only for [HTML anchor (&lt;a&gt;) links](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) and the behavior is the same as `:focus` under Gecko. There is no support for `:focus` in IE.

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

`alinkColor`

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

1.2-11

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/alinkColor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/alinkColor</a>
