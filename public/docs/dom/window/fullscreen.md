Window.fullScreen
=================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `fullScreen` property of the `Window` interface indicates whether the window is displayed in full screen mode or not.

Syntax
------

    isInFullScreen = windowRef.fullScreen;

With chrome privileges, the property is read-write, otherwise it is read-only. Bear in mind that if you try to set this property without chrome privileges, it will not throw an exception and instead just silently fail. This is to prevent scripts designed to set this property in Internet Explorer from breaking.

### Return value

`isInFullScreen`  
A boolean. Possible Values:

-   `true`: The window is in full screen mode.
-   `false`: The window is not in full screen mode.

Notes
-----

-   Switching between regular window and full screen will fire the "resize" event on the corresponding window.

Example
-------

    if (window.fullScreen) {
      // it's fullscreen!
    }
    else {
      // not fullscreen!
    }

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

`fullScreen`

No

No

1

No

No

No

No

No

4

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/fullScreen" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/fullScreen</a>
