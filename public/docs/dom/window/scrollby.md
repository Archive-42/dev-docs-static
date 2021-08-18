Window.scrollBy()
=================

The `Window.scrollBy()` method scrolls the document in the window by the given amount.

Syntax
------

    window.scrollBy(x-coord, y-coord);
    window.scrollBy(options)

### Parameters

-   `x-coord` is the horizontal pixel value that you want to scroll by.
-   `y-coord` is the vertical pixel value that you want to scroll by.

\- or -

-   `options` is a [`ScrollToOptions`](../scrolltooptions) dictionary.

Examples
--------

To scroll down one page:

    window.scrollBy(0, window.innerHeight);

To scroll up:

    window.scrollBy(0, -window.innerHeight);

Using `options`:

    window.scrollBy({
      top: 100,
      left: 100,
      behavior: 'smooth'
    });

Notes
-----

`window.scrollBy()` scrolls by a particular amount, whereas [`window.scroll()`](scroll) scrolls to an absolute position in the document. See also [`window.scrollByLines()`](scrollbylines) and [`window.scrollByPages()`](scrollbypages).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-window-scrollby">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'window.scrollBy()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`scrollBy`

1

79

12-79

Only `scrollBy(x-coord, y-coord)` is supported.

1

11

Only `scrollBy(x-coord, y-coord)` is supported.

3

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

No

45

45

Yes

32

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollBy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/scrollBy</a>
