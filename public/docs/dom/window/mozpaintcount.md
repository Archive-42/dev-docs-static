Window.mozPaintCount
====================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Returns the number of times the current document has been painted to the screen in this window.

Syntax
------

    var paintCount = window.mozPaintCount;

-   `paintCount` stores the `window.mozPaintCount` property value.
-   The `window.mozPaintCount` value is a `long long`, and starts at zero when the document is first created, incrementing by one each time the document is painted.

Specifications
--------------

Not part of any W3C technical specification or recommendation.

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

`mozPaintCount`

No

No

4-72

No

No

No

No

No

4-79

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/mozPaintCount" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/mozPaintCount</a>
