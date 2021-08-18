FontFace.display
================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `display` property of the [`FontFace`](../fontface) interface determines how a font face is displayed based on whether and when it is downloaded and ready to use. This property is equivalent to the CSS `font-display` descriptor.

When this property is used, font loading has a timeline with three periods. The lengths of the first two periods depend on the value of the property and the user agent. (See below.)

block period  
The browser invisibly prepares a fallback font. If the font face loads during this time, it's used to display the text and display is complete.

swap period  
If the font face is still not loaded, the fallback font will be shown. When the font face loads, the fallback will be swapped for the downloaded font.

failure period  
If the font face still is not loaded, the fallback font will be shown and no swap will occur.

Syntax
------

    var display = FontFace.display
    FontFace.display = display

### Value

A [`CSSOMString`](../cssomstring) with one of the following values.

-   `'auto'`: Use the font display strategy provided by the user agent.
-   `'block'`: Gives the font face a short block period and an infinite swap period. The spec recommends 3 seconds for the block period, though this may vary from browser to browser.
-   `'fallback'`: Gives the font face a short block period and a short swap period. The spec recommends 100 ms or less for the block period and 3 seconds for the swap period, though these values may vary from browser to browser.
-   `'optional'`: Gives the font face a short block period and no swap period. The spec recommends 100 ms or less, though this may vary from browser to browser.
-   `'swap'`: Gives the font face a 0 second block period and an infinite swap period.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-font-loading/#dom-fontface-family">CSS Font Loading Module Level 3<br />
<span class="small">The definition of 'display' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-fonts-4/#descdef-font-face-font-display">CSS Fonts Module Level 4<br />
<span class="small">The definition of 'font-display' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Defines the values for the <code>display</code> property. (They are the same as for <code>font-display</code>.)</td></tr></tbody></table>

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

`display`

60

79

58

No

47

10

60

60

No

44

10

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FontFace/display" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FontFace/display</a>
