Window.innerWidth
=================

The read-only [`Window`](../window) property `innerWidth` returns the interior width of the window in pixels. This includes the width of the vertical scroll bar, if one is present.

More precisely, `innerWidth` returns the width of the window's [visual viewport](https://developer.mozilla.org/en-US/docs/Glossary/Visual_Viewport). The interior height of the window—the height of the layout viewport—can be obtained from the [`innerHeight`](innerheight) property.

Syntax
------

    let intViewportWidth = window.innerWidth;

### Value

An integer value indicating the width of the window's layout viewport in pixels. This property is read-only, and has no default value.

To change the window's width, use one of the [`Window`](../window) methods for resizing windows, such as [`resizeBy()`](resizeby) or [`resizeTo()`](resizeto).

Usage notes
-----------

If you need to obtain the width of the window minus the scrollbar and borders, use the root [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element's [`clientWidth`](../element/clientwidth) property instead.

The `innerWidth` property is available on any window or object that behaves like a window, such as a frame or tab.

Example
-------

    // This will return the width of the viewport
    var intFrameWidth = window.innerWidth;

    // This will return the width of the frame viewport within a frameset
    var intFrameWidth = self.innerWidth;

    // This will return the width of the viewport of the closest frameset
    var intFramesetWidth = parent.innerWidth;

    // This will return the width of the viewport of the outermost frameset
    var intOuterFramesetWidth = top.innerWidth;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-window-innerwidth">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'window.innerWidth' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`innerWidth`

1

12

1

4-24

This property was buggy and could give a wrong value before page load in certain circumstances, see [bug 641188](https://bugzil.la/641188).

9

9

3

1

18

4

4-24

This property was buggy and could give a wrong value before page load in certain circumstances, see [bug 641188](https://bugzil.la/641188).

10.1

1

This property returns the width of the [visual viewport](https://developer.mozilla.org/docs/Glossary/visual_viewport) instead of the layout viewport. See [this bug](https://webkit.org/b/174362) for details.

1.0

See also
--------

-   [`window.outerWidth`](outerwidth)
-   [`window.innerHeight`](innerheight)
-   [`window.outerHeight`](outerheight)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/innerWidth" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/innerWidth</a>
