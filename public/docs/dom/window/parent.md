Window.parent
=============

The `Window.parent` property is a reference to the parent of the current window or subframe.

If a window does not have a parent, its `parent` property is a reference to itself.

When a window is loaded in an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe), [`<object>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/object), or [`<frame>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame), its parent is the window with the element embedding the window.

Syntax
------

    var parentWindow = window.parent;

Example
-------

    if (window.parent != window.top) {
      // We're deeper than one down
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-parent">HTML Living Standard<br />
<span class="small">The definition of 'window.parent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`parent`

1

12

1

9

3

1.3

1

18

4

10.1

1

1.0

See also
--------

-   [`window.frameElement`](frameelement) returns the specific element (such as `<iframe>`) the `window` is embedded into.
-   [`window.top`](top) returns a reference to the top-level window.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/parent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/parent</a>
