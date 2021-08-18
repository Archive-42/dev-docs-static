Window.resizeBy()
=================

The `Window.resizeBy()` method resizes the current window by a specified amount.

Syntax
------

    window.resizeBy(xDelta, yDelta)

### Parameters

-   `xDelta` is the number of pixels to grow the window horizontally.
-   `yDelta` is the number of pixels to grow the window vertically.

Example
-------

    // Shrink the window
    window.resizeBy(-200, -200);

Notes
-----

This method resizes the window relative to its current size. To resize the window in absolute terms, use [`window.resizeTo()`](resizeto).

### Creating and resizing an external window

For security reasons, it's no longer possible in Firefox for a website to change the default size of a window in a browser if the window wasn’t created by `window.open()`, or contains more than one tab. See the compatibility table for details on the change.

Even if you create window by `window.open()` **it is not resizable by default.** To make the window resizable, you must open it with the `"resizable"` feature.

    // Create resizable window
    myExternalWindow = window.open("http://myurl.domain", "myWindowName", "resizable");

    // Resize window to 500x500
    myExternalWindow.resizeTo(500, 500);

    // Make window relatively smaller to 400x400
    myExternalWindow.resizeBy(-100, -100);

The window you create must respect the Same Origin Policy. If the window you open is not in the same orgin as the current window, you will not be able to resize, or access any information on, that window/tab.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-window-resizeby">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'window.resizeBy()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`resizeBy`

1

12

1

Since Firefox 7, it's no longer possible for a web site to change the default size of a window in a browser if the window wasn't created by `window.open` or contains more than one tab. [See here](https://bugzil.la/565541#c24) for more details.

4

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/resizeBy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/resizeBy</a>
