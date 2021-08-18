Window.screen
=============

The [`Window`](../window) property `screen` returns a reference to the screen object associated with the window. The `screen` object, implementing the [`Screen`](../screen) interface, is a special object for inspecting properties of the screen on which the current window is being rendered.

Syntax
------

    let screenObj = window.screen;

Example
-------

    if (screen.pixelDepth < 8) {
      // use low-color version of page
    } else {
      // use regular, colorful page
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-window-screen">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'window.screen' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`screen`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/screen" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/screen</a>
