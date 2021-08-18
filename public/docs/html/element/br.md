&lt;br&gt;: The Line Break element
==================================

The `<br>` produces a line break in text (carriage-return). It is useful for writing a poem or an address, where the division of lines is significant.

As you can see from the above example, a `<br>` element is included at each point where we want the text to break. The text after the `<br>` begins again at the start of the next line of the text block.

**Note**: Do not use `<br>` to create margins between paragraphs; wrap them in [`<p>`](p) elements and use the [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) property to control their size.

Attributes
----------

This element's attributes include the [global attributes](../global_attributes).

### Deprecated attributes

`clear`  
Indicates where to begin the next line after the break.

Styling with CSS
----------------

The `<br>` element has a single, well-defined purpose — to create a line break in a block of text. As such, it has no dimensions or visual output of its own, and there is very little you can do to style it.

You can set a [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) on `<br>` elements themselves to increase the spacing between the lines of text in the block, but this is a bad practice — you should use the [`line-height`](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height) property that was designed for that purpose.

Examples
--------

### Simple br

In the following example we use `<br>` elements to create line breaks between the different lines of a postal address:

    Mozilla<br>
    331 E. Evelyn Avenue<br>
    Mountain View, CA<br>
    94041<br>
    USA<br>

The result looks like so:

Accessibility concerns
----------------------

Creating separate paragraphs of text using `<br>` is not only bad practice, it is problematic for people who navigate with the aid of screen reading technology. Screen readers may announce the presence of the element, but not any content contained within `<br>`s. This can be a confusing and frustrating experience for the person using the screen reader.

Use `<p>` elements, and use CSS properties like [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) to control their spacing.

Technical summary
-----------------

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="even"><td>Permitted content</td><td>None, it is an <a href="https://developer.mozilla.org/en-US/docs/Glossary/Empty_element">empty element</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>Must have a start tag, and must not have an end tag. In XHTML documents, write this element as <code>&lt;br /&gt;</code>.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td><code>none</code>, <code>presentation</code></td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLBRElement"><code>HTMLBRElement</code></a></td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-br-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;br&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-br-element">HTML5<br />
<span class="small">The definition of '&lt;br&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/text.html#h-9.3.2.1">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;br&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`br`

1

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

`clear`

1

12

1

Yes

Yes

Yes

Yes

Yes

4

Yes

Yes

Yes

See also
--------

-   [`<address>`](address) element
-   [`<p>`](p) element
-   [`<wbr>`](wbr) element

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br</a>
