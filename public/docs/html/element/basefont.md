&lt;basefont&gt;
================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The obsolete **HTML Base Font element** (`<basefont>`) sets a default font face, size, and color for the other elements which are descended from its parent element. With this set, the font's size can then be varied relative to the base size using the [`<font>`](font) element.

You should not use this element; instead, you should use CSS properties such as [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font), [`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family), [`font-size`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-size), and [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) to change the font configuration for an element and its contents.

Attributes
----------

Like all other HTML elements, this element supports the [global attributes](../global_attributes).

`color`  
This attribute sets the text color using either a named color or a color specified in the hexadecimal \#RRGGBB format.

`face`  
This attribute contains a list of one or more font names. The document text in the default style is rendered in the first font face that the client's browser supports. If no font listed is installed on the local system, the browser typically defaults to the proportional or fixed-width font for that system.

`size`  
This attribute specifies the font size as either a numeric or relative value. Numeric values range from 1 to 7 with 1 being the smallest and 3 the default.

Usage notes
-----------

**Do not use this element!** Though once (imprecisely) normalized in HTML 3.2, it wasn't supported in all major browsers. Further, browsers, and even successive versions of browsers, never implemented it in the same way: practically, using it has always brought *indeterminate* results.

The `<basefont>` element was deprecated in the standard at the same time as all elements related to styling only. Starting with HTML 4, HTML does not convey styling information anymore (outside the [`<style>`](style) element or the **style** attribute of each element). In HTML5, this element has been removed completely. For any new web development, styling should be written using [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) only.

The former behavior of the [`<font>`](font) element can be achieved, and even better controlled using the [CSS Fonts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Fonts) properties.

DOM interface
-------------

This element implements the [`HTMLBaseFontElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLBaseFontElement) interface.

Example
-------

    <basefont color="#FF0000" face="Helvetica" size="+2" />

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

`basefont`

No

12-79

1-4

Yes

No

No

No

No

No

No

No

No

Notes
-----

-   HTML 3.2 supports the basefont element but only with the size attribute.
-   The strict HTML and XHTML specifications do not support this element.
-   Despite being part of transitional standards, some standards-focused browsers like Mozilla and Opera do not support this element.
-   This element can be imitated with a CSS rule on the [`<body>`](body) element.
-   XHTML 1.0 requires a trailing slash for this element: `<basefont />`.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/basefont" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/basefont</a>
