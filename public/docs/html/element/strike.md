&lt;strike&gt;
==============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `<strike>` (or *HTML Strikethrough Element*) places a strikethrough (horizontal line) over text.

**Usage note:** This element is deprecated in HTML 4 and XHTML 1, and obsoleted in HTML5. If semantically appropriate, i.e., if it represents *deleted* content, use [`<del>`](del) instead. In all other cases use [`<s>`](s).

<table><tbody><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

Example
-------

    &lt;strike&gt;: <strike>Today's Special: Salmon</strike> SOLD OUT<br />
    &lt;s&gt;:    <s>Today's Special: Salmon</s> SOLD OUT

The result of this code is:

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/html52/obsolete.html#strike">HTML5<br />
<span class="small">The definition of '&lt;strike&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Make obsolete in favor of <a href="del"><code>&lt;del&gt;</code></a> and <a href="s"><code>&lt;s&gt;</code></a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html401//present/graphics.html#edef-STRIKE">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;strike&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Make deprecated in favor of <a href="del"><code>&lt;del&gt;</code></a> and <a href="s"><code>&lt;s&gt;</code></a>.</td></tr></tbody></table>

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

`strike`

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

-   The [`<s>`](s) element.
-   The [`<del>`](del) element should be used if the data has been *deleted*.
-   The CSS [`text-decoration`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration) property can be used to style text with a strikethrough.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strike" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strike</a>
