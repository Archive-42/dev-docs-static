Screen.colorDepth
=================

The `Screen.colorDepth` read-only property returns the color depth of the screen. Per the CSSOM, some implementations return `24` for compatibility reasons. See the browser compatibility section for those that don't.

Syntax
------

    bitDepth = window.screen.colorDepth;

Example
-------

    // Check the color depth of the screen
    if ( window.screen.colorDepth < 8) {
      // Use low-color version of page
    } else {
      // Use regular, colorful page
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-screen-colordepth">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Screen.colorDepth' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`colorDepth`

1

Starting with version 59 this property is no longer required to always return 24.

12

1

4

≤12.1

1

1

Starting with version 59 this property is no longer required to always return 24.

18

Starting with version 59 this property is no longer required to always return 24.

4

≤12.1

1

1.0

Starting with Samsung Internet 7.0 this property is no longer required to always return 24.

See also
--------

-   [`Screen.pixelDepth`](pixeldepth)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Screen/colorDepth" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Screen/colorDepth</a>
