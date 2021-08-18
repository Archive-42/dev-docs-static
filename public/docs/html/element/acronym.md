&lt;acronym&gt;
===============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Summary
-------

The HTML Acronym Element (`<acronym>`) allows authors to clearly indicate a sequence of characters that compose an acronym or abbreviation for a word.

**Usage note:** This element has been removed in HTML5 and shouldn't be used anymore. Instead web developers should use the [`<abbr>`](abbr) element.

Attributes
----------

This element only has [global attributes](../global_attributes), which are common to all elements.

DOM Interface
-------------

This element implements the [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) interface.

**Implementation note:** Up to Gecko 1.9.2 inclusive, Firefox implements the [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement) interface for this element.

Example
-------

    <p>The <acronym title="World Wide Web">WWW</acronym> is only a component of the Internet.</p>

Default styling
---------------

Though the purpose of this tag is purely for the convenience of the author, its default styling varies from one browser to another:

-   Some browsers, like Internet Explorer, do not style it differently than a [`<span>`](span) element.
-   Opera, Firefox, Chrome, and some others add a dotted underline to the content of the element.
-   A few browsers not only add a dotted underline, but also put it in small caps; to avoid this styling, adding something like [`font-variant`](https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant)`: none` in the CSS takes care of this case.

It is therefore recommended that web authors either explicitly style this element, or accept some cross-browser variation.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/text.html#edef-ACRONYM">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;acronym&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`acronym`

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

-   The [`<abbr>`](abbr) HTML element

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/acronym" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/acronym</a>
