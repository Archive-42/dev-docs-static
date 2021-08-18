Window.scrollTo()
=================

`Window.scrollTo()` scrolls to a particular set of coordinates in the document.

Syntax
------

    window.scrollTo(x-coord, y-coord)
    window.scrollTo(options)

### Parameters

-   `x-coord` is the pixel along the horizontal axis of the document that you want displayed in the upper left.
-   `y-coord` is the pixel along the vertical axis of the document that you want displayed in the upper left.

\- or -

-   `options` is a [`ScrollToOptions`](../scrolltooptions) dictionary.

Examples
--------

    window.scrollTo(0, 1000);

Using `options`:

    window.scrollTo({
      top: 100,
      left: 100,
      behavior: 'smooth'
    });

Notes
-----

[`Window.scroll()`](scroll) is effectively the same as this method. For relative scrolling, see [`Window.scrollBy()`](scrollby), [`Window.scrollByLines()`](scrollbylines), and [`Window.scrollByPages()`](scrollbypages).

For scrolling elements, see [`Element.scrollTop`](../element/scrolltop) and [`Element.scrollLeft`](../element/scrollleft).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-window-scroll">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'window.scroll()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`scrollTo`

1

12

1

4

4

1

1

18

4

10.1

1

1.0

`ScrollToOptions`

45

79

Yes

No

32

10

45

45

Yes

32

10

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollTo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollTo</a>
