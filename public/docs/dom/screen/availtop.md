Screen.availTop
===============

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Specifies the y-coordinate of the first pixel that is not allocated to permanent or semipermanent user interface features.

Syntax
------

    let availTop = window.screen.availTop;

Example
-------

    let setX = window.screen.width - window.screen.availLeft;
    let setY = window.screen.height - window.screen.availTop;
    window.moveTo(setX, setY);

Notes
-----

In most cases, this property returns `0`.

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

`availTop`

1

79

1

No

15

1

1

18

4

14

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Screen/availTop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Screen/availTop</a>
