Screen.pixelDepth
=================

Returns the bit depth of the screen. Per the CSSOM, some implementations return `24` for compatibility reasons. See the [browser compatibility](#browser%0A__compatibility) section for those that don't.

Syntax
------

    let depth = window.screen.pixelDepth

Example
-------

    // if there is not adequate bit depth
    // choose a simpler color
    if ( window.screen.pixelDepth > 8 ) {
      document.style.color = "#FAEBD7";
    } else {
      document.style.color = "#FFFFFF";
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-screen-pixeldepth">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Screen.pixelDepth' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`pixelDepth`

1

Starting with version 59 this property is no longer required to always return 24.

12

1

9

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

-   [`Screen.colorDepth`](colordepth)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Screen/pixelDepth" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Screen/pixelDepth</a>
