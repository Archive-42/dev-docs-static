Window.setCursor()
==================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `Window.setCursor()` method sets the cursor for the current window.

Example
-------

    function setBusyCursor(enable) {
      window.setCursor(enable ? "wait" : "auto");
    }

Notes
-----

The cursor isn't reset until it's set back to `auto`.

This function is a part of [ChromeWindow interface](https://developer.mozilla.org/en-US/docs/XPCOM_Interface_Reference/nsIDOMChromeWindow). This function is unavailable to web pages, which can use the CSS [`cursor`](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor) property instead.

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

`setCursor`

No

No

No

No

?

No

No

No

No

?

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/setCursor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/setCursor</a>
