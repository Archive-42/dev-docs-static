&lt;spacer&gt;
==============

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

`<spacer>` is an obsolete HTML element which allowed insertion of empty spaces on pages. It was devised by Netscape to accomplish the same effect as a single-pixel layout image, which was something web designers used to use to add white spaces to web pages without actually using an image. However, `<spacer>` no longer supported by any major browser and the same effects can now be achieved using simple CSS.

Firefox, which is the descendant of Netscape's browsers, removed support for `<spacer>` in version 4.

Attributes
----------

Like all other HTML elements, this element supports the [global attributes](../global_attributes).

`type`  
This attribute determines type of spacer. Possible values are `horizontal`, `vertical` and `block`.

`size`  
This attribute can be used for defining size of spacer in pixels when type is `horizontal` or `vertical`.

`width`  
This attribute can be used for defining width of spacer in pixels when type is `block`.

`height`  
This attribute can be used for defining height of spacer in pixels when type is `block`.

`align`  
This attribute determines alignment of spacer. Possible values are `left`, `right` and `center`.

Example
-------

    <span>Just a text node</span>
    <spacer type="horizontal" size="10"></spacer>
    <span>Just another text node</span>
    <spacer type="block" width="10" height="10"></spacer>

Specifications
--------------

Not part of any specification.

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

`spacer`

No

No

1-4

No

No

No

No

No

No

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/spacer" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/spacer</a>
