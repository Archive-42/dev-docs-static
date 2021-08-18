Screen.mozBrightness
====================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Indicates how bright the screen's backlight is, on a scale from 0 (very dim) to 1 (full brightness); this value is a double-precision float.

You can read and write this attribute even when the screen is disabled, but the backlight is off while the screen is disabled. If you write a value of X into this attribute, the attribute may not have the same value X when you later read it. Most screens don't support as many different brightness levels as there are doubles between 0 and 1. The value's precision might be reduced before storing it.

Syntax
------

    let screenBrightness = window.screen.mozBrightness;

Specifications
--------------

Not part of specification.

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

`mozBrightness`

No

No

12

No

No

No

No

No

14

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Screen/mozBrightness" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Screen/mozBrightness</a>
