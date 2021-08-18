HTMLImageElement.lowsrc
=======================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The [`HTMLImageElement`](../htmlimageelement) interface's *obsolete* `lowsrc` property can be used to specify the URL of a reduced-quality or otherwise faster-loading version of the image specified by the [`src`](src) property.

This property reflects the [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) [`lowsrc`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-lowsrc) attribute.

Syntax
------

    htmlImageElement.lowsrc = imageUrl;
    imageUrl = htmlImageElement.lowsrc;

### Value

A [`DOMString`](../domstring) specifying the URL of a version of the image specified by `src` which has been modified in some fashion so that it loads significantly more quickly than the primary image.

There are a number of ways to achieve this; primary among them:

-   Higher compression levels (for example, a primary image saved as a JPEG using 85% quality might have a `lowsrc` version saved at 15%.
-   Reduced color depth; a primary image in 32-bit color might have an alternate image in 8-bit color.

**Important:** The `lowsrc` property is obsolete and should not be used. Instead, you should use an image format which loads progressively (such as progressive JPEG). Or make sure your images are all well-optimized and balanced for appearance versus size.

Usage notes
-----------

`lowsrc` is a strange case. It was never technically part of the HTML specification (it was a Mozilla extension to HTML); however, HTML 5 does list it among the obsolete attributes.

Browser compatibility
---------------------

No compatibility data found for `api.HTMLImageElement.lowSrc`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/lowSrc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/lowSrc</a>
