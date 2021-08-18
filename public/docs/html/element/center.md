&lt;center&gt;: The Centered Text element
=========================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The obsolete **HTML Center Element** (`<center>`) is a [block-level element](../block-level_elements) that displays its block-level or inline contents centered horizontally within its containing element. The container is usually, but isn't required to be, [`<body>`](body).

This tag has been deprecated in HTML 4 (and XHTML 1) in favor of the [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) property, which can be applied to the [`<div>`](div) element or to an individual [`<p>`](p). For centering blocks, use other CSS properties like [`margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left) and [`margin-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right) and set them to `auto` (or set [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) to `0 auto`).

DOM interface
-------------

This element implements the [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) interface.

**Implementation note:** up to Gecko 1.9.2 inclusive, Firefox implements the [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement) interface for this element.

Example 1
---------

    <center>This text will be centered.
    <p>So will this paragraph.</p></center>

Example 2 (CSS alternative)
---------------------------

    <div style="text-align:center">This text will be centered.
    <p>So will this paragraph.</p></div>

Example 3 (CSS alternative)
---------------------------

    <p style="text-align:center">This line will be centered.<br>
    And so will this line.</p>

Note
----

Applying [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)`:center` to a [`<div>`](div) or [`<p>`](p) element centers the *contents* of those elements while leaving their overall dimensions unchanged.

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

`center`

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

-   [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)
-   [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/center" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/center</a>
