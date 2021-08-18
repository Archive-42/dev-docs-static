# Document.height

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note:** Starting in Gecko 6.0, `document.height` is no longer supported. Instead, use `document.body.clientHeight`. See [`element.clientHeight`](../element/clientheight).

Returns the height of the [`document`](../document) object. In most cases, this is equal to the [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) element of the current document.

## Syntax

    pixels = document.height

## Example

    // alert document height
    alert(document.height);

## Alternatives

    document.body.clientHeight
    document.documentElement.clientHeight
    document.documentElement.scrollHeight

## Specifications

HTML5

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

`height`

1-31

No

1-6

No

15-18

1-10

1-4.4.3

18-31

4-6

14-18

1-10

1.0-3.0

## See also

- [`document.width`](width)
- [`Element.clientHeight`](../element/clientheight)
- [`Element.scrollHeight`](../element/scrollheight)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/height" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/height</a>
