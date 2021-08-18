&lt;xmp&gt;
===========

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Summary
-------

The *HTML Example Element* (`<xmp>`) renders text between the start and end tags without interpreting the HTML in between and using a monospaced font. The HTML2 specification recommended that it should be rendered wide enough to allow 80 characters per line.

**Note:** Do not use this element.

-   It has been deprecated since HTML3.2 and was not implemented in a consistent way. It was completely removed from the language in HTML5.
-   Use the [`<pre>`](pre) element or, if semantically adequate, the [`<code>`](code) element instead. Note that you will need to escape the '`<`' character as '`&lt;`' to make sure it is not interpreted as markup.
-   A monospaced font can also be obtained on any element, by applying an adequate [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) style using `monospace` as the generic-font value for the [`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family) property.

Attributes
----------

This element has no other attributes than the [global attributes](../global_attributes), common to all elements.

DOM interface
-------------

This element implements the [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) interface.

**Implementation note:** up to Gecko 1.9.2 inclusive, Firefox implements the [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement) interface for this element.

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

`xmp`

Yes

12

Yes

Before Firefox 4, this element implemented the `HTMLSpanElement` interface instead of the standard `HTMLElement` interface.

Yes

Yes

Yes

Yes

Yes

Yes

Before Firefox 4, this element implemented the `HTMLSpanElement` interface instead of the standard `HTMLElement` interface.

Yes

Yes

Yes

See also
--------

-   The [`<pre>`](pre) and [`<code>`](code) elements to be used instead.
-   The [`<plaintext>`](plaintext) and [`<listing>`](listing) elements, similar to [`<xmp>`](xmp) but also obsolete.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/xmp" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/xmp</a>
