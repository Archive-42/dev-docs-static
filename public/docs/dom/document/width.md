# Document.width

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note:** Starting in Gecko 6.0, `document.width` is no longer supported. Instead, use `document.body.clientWidth`. See [`element.clientWidth`](../element/clientwidth).

Returns the width of the [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) element of the current document in pixels.

Not supported by Internet Explorer.

## Syntax

    pixels = document.width;

## Example

    function init() {
      alert("The width of the document is " + document.width + " pixels.");
    }

## Alternatives

    document.body.clientWidth              /* width of <body> */
    document.documentElement.clientWidth   /* width of <html> */
    window.innerWidth                      /* window's width */

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

`width`

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

- [`document.height`](height)
- [`Element.clientWidth`](../element/clientwidth)
- [`Element.scrollWidth`](../element/scrollwidth)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/width</a>
