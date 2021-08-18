Window.resizeTo()
=================

The `Window.resizeTo()` method dynamically resizes the window.

Syntax
------

    window.resizeTo(width, height)

### Parameters

`width`  
An integer representing the new [`outerWidth`](outerwidth) in pixels (including scroll bars, title bars, etc).

`height`  
An integer value representing the new [`outerHeight`](outerheight) in pixels (including scroll bars, title bars, etc).

Example
-------

This function resizes the window so that it takes up one quarter of the available screen. See the [`Screen.availWidth`](../screen/availwidth) and [`Screen.availHeight`](../screen/availheight) properties.

    function quarter() {
      window.resizeTo(
        window.screen.availWidth / 2,
        window.screen.availHeight / 2
      );
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-window-resizeto">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'window.resizeTo()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`resizeTo`

1

12

1

Since Firefox 7, it's no longer possible for a web site to change the default size of a window in a browser if the window wasn't created by `window.open` or contains more than one tab. [See here](https://bugzil.la/565541#c24) for more details.

4

≤12.1

1

1

18

4

≤12.1

1

1.0

Note: It's not possible to resize a window or tab that wasn’t created by `window.open()`. It's also not possible to resize when the window has multiple tabs.

See also
--------

-   [`window.resizeBy()`](resizeby)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/resizeTo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/resizeTo</a>
