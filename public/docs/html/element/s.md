&lt;s&gt;
=========

The `<s>` renders text with a strikethrough, or a line through it. Use the `<s>` element to represent things that are no longer relevant or no longer accurate. However, `<s>` is not appropriate when indicating document edits; for that, use the [`<del>`](del) and [`<ins>`](ins) elements, as appropriate.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement"><code>HTMLElement</code></a></td></tr></tbody></table>

Attributes
----------

This element only includes the [global attributes](../global_attributes).

**Implementation note:** Up to Gecko 1.9.2 inclusive, Firefox implements the [`HTMLSpanElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLSpanElement) interface for this element.

Examples
--------

    <s>Today's Special: Salmon</s> SOLD OUT<br>
    <span style="text-decoration:line-through;">Today's Special:
      Salmon</span> SOLD OUT

Accessibility concerns
----------------------

The presence of the `s` element is not announced by most screen reading technology in its default configuration. It can be made to be announced by using the CSS [`content`](https://developer.mozilla.org/en-US/docs/Web/CSS/content) property, along with the [`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before) and [`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after) pseudo-elements.

    s::before,
    s::after {
      clip-path: inset(100%);
      clip: rect(1px, 1px, 1px, 1px);
      height: 1px;
      overflow: hidden;
      position: absolute;
      white-space: nowrap;
      width: 1px;
    }

    s::before {
      content: " [start of stricken text] ";
    }

    s::after {
      content: " [end of stricken text] ";
    }

Some people who use screen readers deliberately disable announcing content that creates extra verbosity. Because of this, it is important to not abuse this technique and only apply it in situations where not knowing content has been struck out would adversely affect understanding.

-   [Short note on making your mark (more accessible) | The Paciello Group](https://developer.paciellogroup.com/blog/2017/12/short-note-on-making-your-mark-more-accessible/)
-   [Tweaking Text Level Styles | Adrian Roselli](https://adrianroselli.com/2017/12/tweaking-text-level-styles.html)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-s-element">HTML Living Standard<br />
<span class="small">The definition of 's element' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/textlevel-semantics.html#the-s-element">HTML5<br />
<span class="small">The definition of 's element' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`s`

Yes

12

1

Before Firefox 4, this element implemented the `HTMLSpanElement` interface instead of the standard `HTMLElement` interface.

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

-   The [`<strike>`](strike) element, alter ego of the [`<s>`](s) element is obsolete and should not be used on Web sites any more.
-   The [`<del>`](del) element is to be used instead if the data has been *deleted*.
-   The CSS [`text-decoration-line`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-line) property is to be used to achieve the former visual aspect of the [`<s>`](s) element.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/s" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/s</a>
