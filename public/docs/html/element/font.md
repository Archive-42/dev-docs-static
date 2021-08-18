&lt;font&gt;
============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Summary
-------

The *HTML Font Element* (`<font>`) defines the font size, color and face for its content.

*Usage note:*

**Do not use this element!** Though once normalized in HTML 3.2, it was deprecated in HTML 4.01, at the same time as all elements related to styling only, then made obsolete in HTML5.

Starting with HTML 4, HTML does not convey styling information anymore (outside the [`<style>`](style) element or the **style** attribute of each element). For any new web development, styling should be written using [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) only.

The former behavior of the [`<font>`](font) element can be achieved, and even better controlled using the [CSS Fonts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Fonts) CSS properties.

Attributes
----------

Like all other HTML elements, this element supports the [global attributes](../global_attributes).

`color`  
This attribute sets the text color using either a named color or a color specified in the hexadecimal \#RRGGBB format.

`face`  
This attribute contains a comma-separated list of one or more font names. The document text in the default style is rendered in the first font face that the client's browser supports. If no font listed is installed on the local system, the browser typically defaults to the proportional or fixed-width font for that system.

`size`  
This attribute specifies the font size as either a numeric or relative value. Numeric values range from `1` to `7` with `1` being the smallest and `3` the default. It can be defined using a relative value, like `+2` or `-3`, which set it relative to the value of the [`size`](basefont#attr-size) attribute of the [`<basefont>`](basefont) element, or relative to `3`, the default value, if none does exist.

DOM interface
-------------

This element implements the [`HTMLFontElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLFontElement) interface.

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

`font`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`color`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`face`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`size`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/font" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/font</a>
