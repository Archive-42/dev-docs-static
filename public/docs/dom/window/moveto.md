Window.moveTo()
===============

The `moveTo()` method of the [`Window`](../window) interface moves the current window to the specified coordinates.

**Note:** This function moves the window to an absolute location. In contrast, [`window.moveBy()`](moveby) moves the window relative to its current location.

Syntax
------

    window.moveTo(x, y)

### Parameters

-   `x` is the horizontal coordinate to be moved to.
-   `y` is the vertical coordinate to be moved to.

Example
-------

This example moves the window to the top-left corner of the screen.

    function origin() {
      window.moveTo(0, 0);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-window-moveto">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'window.moveTo()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`moveTo`

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

-   [`Window.moveBy()`](moveby)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/moveTo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/moveTo</a>
