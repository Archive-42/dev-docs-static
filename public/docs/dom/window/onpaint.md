Window.onpaint
==============

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`Window.onpaint` is an event handler for the `paint` event on the window.

Not working in Gecko-based applications currently, see Notes section!

Syntax
------

    window.onpaint = funcRef;

-   `funcRef` is a handler function.

Notes
-----

`onpaint` doesn't work currently, and it is questionable whether this event is going to work at all, see [bug 239074](https://bugzilla.mozilla.org/show_bug.cgi?id=239074).

The `paint` event is raised when the window is rendered. This event occurs after the `load` event for a window, and reoccurs each time the window needs to be re-rendered, such as when another window obscures it and is then cleared away.

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

`onpaint`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/onpaint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/onpaint</a>
