Screen.height
=============

The `Screen.height` read-only property returns the height of the screen in pixels.

Syntax
------

    var height = window.screen.height

Example
-------

    if (window.screen.availHeight !== window.screen.height) {
       // Something is occupying some screen real estate!
    }

Notes
-----

Note that not all of the height given by this property may be available to the window itself. Widgets such as taskbars or other special application windows that integrate with the OS (e.g., the Spinner player minimized to act like an additional toolbar on windows) may reduce the amount of space available to browser windows and other applications.

Internet Explorer will take into account the zoom setting when reporting the screen height. It will only return the real height of the screen if the zoom is set to 100%.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-screen-height">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Screen.height' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`height`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Screen/height" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Screen/height</a>
