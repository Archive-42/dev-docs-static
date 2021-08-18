Screen.width
============

The `Screen.width` read-only property returns the width of the screen in pixels.

Syntax
------

    lWidth = window.screen.width

Example
-------

    // Crude way to check that the screen is at least 1024x768
    if (window.screen.width >= 1024 && window.screen.height >= 768) {
      // Resolution is 1024x768 or above
    }

Notes
-----

Note that not all of the width given by this property may be available to the window itself. When other widgets occupy space that cannot be used by the `window` object, there is a difference in `window.screen.width` and `window.screen.availWidth`. See also [`screen.height`](height).

Internet Explorer will take into account the zoom setting when reporting the screen width. It will only return the real width of the screen if the zoom is set to 100%.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-screen-width">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Screen.width' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`width`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Screen/width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Screen/width</a>
