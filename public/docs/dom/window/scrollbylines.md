Window.scrollByLines()
======================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `Window.scrollByLines()` method scrolls the document by the specified number of lines.

Syntax
------

    window.scrollByLines(lines)

### Parameters

-   `lines` is the number of lines to scroll the document by. It may be a positive or negative integer.

Example
-------

    <!-- Scroll up the document by 5 lines -->
    <button id="scroll-up" onclick="scrollByLines(-5);">Up 5 lines</button>

    <!-- Scroll down the document by 5 lines -->
    <button id="scroll-down" onclick="scrollByLines(5);">Down 5 lines</button>

Specifications
--------------

This is not part of any specification.

Browser compatibility
---------------------

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

`scrollByLines`

No

No

1

No

?

No

No

No

4

?

No

No

See also
--------

-   [`window.scroll()`](scroll)
-   [`window.scrollBy()`](scrollby)
-   [`window.scrollByPages()`](scrollbypages)
-   [`window.scrollTo()`](scrollto)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollByLines" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollByLines</a>
