Window.sizeToContent()
======================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `Window.sizeToContent()` method sizes the window according to its content. In order for it to work, the DOM content should be loaded when this function is called—for example, once the `DOMContentLoaded` event has been thrown.

Since Firefox 20, the mimimal size of the window is clamped to prevent the window from being too small for the user to interact with.

Syntax
------

    window.sizeToContent()

Example
-------

    window.sizeToContent();

Specifications
--------------

This feature is not part of any specification.

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

`sizeToContent`

No

No

1

No

?

No

No

No

4

This method has no effect as a page is always in a tab.

?

No

No

See also
--------

-   [`Window`](../window)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/sizeToContent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/sizeToContent</a>
