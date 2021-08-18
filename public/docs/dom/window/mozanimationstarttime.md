Window.mozAnimationStartTime
============================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Returns the time, in milliseconds since the epoch, at which animations started now should be considered to have started. This value should be used instead of, for example, `Date.now()`, because this value will be the same for all animations started in this window during this refresh interval, allowing them to remain in sync with one another.

This also allows JavaScript-based animations to remain synchronized with CSS transitions and SMIL animations triggered during the same refresh interval.

Syntax
------

    time = window.mozAnimationStartTime;

### Parameters

-   *`time`* is the time in milliseconds since the epoch at which animations for the current window should be considered to have started.

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

`mozAnimationStartTime`

No

No

4-42

No

No

No

No

No

4-42

No

No

No

See also
--------

-   [`window.requestAnimationFrame`](../window/requestanimationframe)
-   [`window.onmozbeforepaint`](onmozbeforepaint)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/mozAnimationStartTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/mozAnimationStartTime</a>
