&lt;listing&gt;
===============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Summary
-------

The *HTML Listing Element* (`<listing>`) renders text between the start and end tags without interpreting the HTML in between and using a monospaced font. The HTML 2 standard recommended that lines shouldn't be broken when not greater than 132 characters.

**Note:** Do not use this element.

-   It is deprecated since HTML 3.2 and was neither implemented by all browsers, nor in a consistent way. Even more it is obsoleted in HTML5 and may be rendered by conforming user-agents as the [`<pre>`](pre) element, which will interpret the internal HTML!
-   Instead use the [`<pre>`](pre) element or if semantically adequate the [`<code>`](code) element, eventually escaping the HTML '`<`' and '`>`' so that they don't get interpreted.
-   A monospaced font can also be obtained on a simple [`<div>`](div) element, by applying an adequate [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) style using `monospace` as the generic-font value in a [`font-family`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-family) property.

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

`listing`

No

No

No

Before Firefox 4, this element implemented the `HTMLSpanElement` interface instead of the standard `HTMLElement` interface.

No

No

No

No

No

No

Before Firefox 4, this element implemented the `HTMLSpanElement` interface instead of the standard `HTMLElement` interface.

No

No

No

See also
--------

-   The [`<pre>`](pre) and [`<code>`](code) elements to be used instead.
-   The [`<plaintext>`](plaintext) and [`<xmp>`](xmp) elements, similar to [`<listing>`](listing) but also obsolete.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/listing" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/listing</a>
