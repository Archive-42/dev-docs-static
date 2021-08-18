&lt;nobr&gt;: The Non-Breaking Text element
===========================================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The non-standard, obsolete HTML `<nobr>` element prevents the text it contains from automatically wrapping across multiple lines, potentially resulting in the user having to scroll horizontally to see the entire width of the text.

Although this element is widely supported, it was *never* standard HTML, so you shouldn't use it. Instead, use the CSS property [`white-space`](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space) like this:

    <span style="white-space: nowrap;">Long line with no breaks</span>

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

`nobr`

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

See also
--------

-   [`white-space`](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space)
-   [`overflow`](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nobr" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/nobr</a>
