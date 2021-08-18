&lt;ins&gt;
===========

The `<ins>` represents a range of text that has been added to a document. You can use the [`<del>`](del) element to similarly represent a range of text that has been deleted from the document.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">Phrasing content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">flow content</a>.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#transparent_content_model">Transparent</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLModElement"><code>HTMLModElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`cite`  
This attribute defines the URI of a resource that explains the change, such as a link to meeting minutes or a ticket in a troubleshooting system.

`datetime`  
This attribute indicates the time and date of the change and must be a valid date with an optional time string. If the value cannot be parsed as a date with an optional time string, the element does not have an associated time stamp. For the format of the string without a time, see [Format of a valid date string](../date_and_time_formats#date_strings). The format of the string if it includes both date and time is covered in [Format of a valid local date and time string](../date_and_time_formats#local_date_and_time_strings).

Examples
--------

    <ins>This text has been inserted</ins>

### Result

Accessibility concerns
----------------------

The presence of the `<ins>` element is not announced by most screen reading technology in its default configuration. It can be made to be announced by using the CSS [`content`](https://developer.mozilla.org/en-US/docs/Web/CSS/content) property, along with the [`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before) and [`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after) pseudo-elements.

    ins::before,
    ins::after {
      clip-path: inset(100%);
      clip: rect(1px, 1px, 1px, 1px);
      height: 1px;
      overflow: hidden;
      position: absolute;
      white-space: nowrap;
      width: 1px;
    }

    ins::before {
      content: " [insertion start] ";
    }

    ins::after {
      content: " [insertion end] ";
    }

Some people who use screen readers deliberately disable announcing content that creates extra verbosity. Because of this, it is important to not abuse this technique and only apply it in situations where not knowing content has been inserted would adversely affect understanding.

-   [Short note on making your mark (more accessible) | The Paciello Group](https://developer.paciellogroup.com/blog/2017/12/short-note-on-making-your-mark-more-accessible/)
-   [Tweaking Text Level Styles | Adrian Roselli](https://adrianroselli.com/2017/12/tweaking-text-level-styles.html)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/edits.html#the-ins-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;ins&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/edits.html#the-ins-element">HTML5<br />
<span class="small">The definition of '&lt;ins&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/text.html#h-9.4">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;ins&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`ins`

Yes

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

`cite`

Yes

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

`datetime`

Yes

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

-   [`<del>`](del) element for marking deletion into a document

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ins" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ins</a>
