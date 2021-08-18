Window.moveBy()
===============

The `moveBy()` method of the [`Window`](../window) interface moves the current window by a specified amount.

**Note:** This function moves the window relative to its current location. In contrast, [`window.moveTo()`](moveto) moves the window to an absolute location.

Syntax
------

    window.moveBy(deltaX, deltaY)

### Parameters

-   `deltaX` is the amount of pixels to move the window horizontally. Positive values are to the right, while negative values are to the left.
-   `deltaY` is the amount of pixels to move the window vertically. Positive values are down, while negative values are up.

Example
-------

This example moves the window 10 pixels to the right and 10 pixels up.

    function budge() {
      moveBy(10, -10);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-window-moveby">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'window.moveBy()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`moveBy`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

As of Firefox 7, websites can no longer move a browser window [in the following cases](https://bugzilla.mozilla.org/show_bug.cgi?id=565541#c24):

1.  You can't move a window or tab that wasn’t created by [`Window.open()`](open).
2.  You can't move a window or tab when it’s in a window with more than one tab.

See also
--------

-   [`Window.moveTo()`](moveto)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/moveBy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/moveBy</a>
