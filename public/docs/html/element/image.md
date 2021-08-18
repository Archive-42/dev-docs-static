&lt;image&gt;: The Image element
================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The obsolete `<image>` is an obsolete remnant of an ancient version of HTML lost in the mists of time; use the standard [`<img>`](img) element instead. Seriously, the specification even literally uses the words "Don't ask" when describing this element.

**Do not use this!** In order to display images, use the standard [`<img>`](img) element.

While some browsers will attempt to automatically convert this into an [`<img>`](img) element, they won't always do so, and won't always succeed when they try, due to various ways in which the options can be interpreted. So just don't use it if you like your users.

Specifications
--------------

This might have once been part of a specification, but nobody seems to remember. It certainly isn't anymore. Just avoid it like the plague.

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

`image`

?

?

Yes

Before Firefox 22, creating an &lt;image&gt; element incorrectly resulted in an `HTMLSpanElement` object, instead of the expected `HTMLElement`.

?

?

?

?

?

Yes

Before Firefox 22, creating an &lt;image&gt; element incorrectly resulted in an `HTMLSpanElement` object, instead of the expected `HTMLElement`.

?

?

?

In general, browsers will attempt to map this to `<img>`, but only if the [`src`](img#attr-src) attribute is specified as well. Creating an `<image>` element without a `src` attribute results in an [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) object with the local element name `"image"`. However, if the element is created with a `src` attribute, the result is instead an [`HTMLImageElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement) and its local element name is changed to `"img"`.

However, that doesn't mean this is a good idea to use. It's not.

See also
--------

-   [`<img>`](img): The correct way to display an image in a document
-   [`<picture>`](picture): A more powerful correct way to display an image in a document

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/image" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/image</a>
