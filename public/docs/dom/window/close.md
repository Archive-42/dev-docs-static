Window.close()
==============

The `Window.close()` method closes the current window, or the window on which it was called.

This method can only be called on windows that were opened by a script using the [`Window.open()`](open) method. If the window was not opened by a script, an error similar to this one appears in the console: `Scripts may not close windows that were not opened by script.`

Note also that `close()` has no effect when called on [`Window`](../window) objects returned by `HTMLIFrameElement.contentWindow`.

Syntax
------

    window.close();

Examples
--------

### Closing a window opened with `window.open()`

This example shows a method which opens a window and a second one which closes the window; this demonstrates how to use `Window.close()` to close a window opened by calling [`window.open()`](open).

    //Global var to store a reference to the opened window
    var openedWindow;

    function openWindow() {
      openedWindow = window.open('moreinfo.htm');
    }

    function closeOpenedWindow() {
      openedWindow.close();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-window-close">HTML Living Standard<br />
<span class="small">The definition of 'window.close()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#dom-window-close">HTML5<br />
<span class="small">The definition of 'Window.close()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`close`

1

12

Before Edge 79, scripts can close windows that weren't opened by the same script.

1

Before Firefox 46, scripts can close windows that weren't opened by the same script.

4

3

1

1

18

4

Before Firefox 46, scripts can close windows that weren't opened by the same script.

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/close" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/close</a>
