&lt;col&gt;
===========

The `<col>` defines a column within a table and is used for defining common semantics on all common cells. It is generally found within a [`<colgroup>`](colgroup) element.

`<col>` allows styling columns using CSS, but only a few properties will have an effect on the column ([see the CSS 2.1 specification](https://www.w3.org/TR/CSS21/tables.html#columns) for a list).

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td>None, it is an <a href="https://developer.mozilla.org/en-US/docs/Glossary/Empty_element">empty element</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>It must have start tag, but must not have an end tag.</td></tr><tr class="even"><td>Permitted parents</td><td><a href="colgroup"><code>&lt;colgroup&gt;</code></a> only, though it can be implicitly defined as its start tag is not mandatory. The <a href="colgroup"><code>&lt;colgroup&gt;</code></a> must not have a <a href="colgroup#attr-span"><code>span</code></a> attribute.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://www.w3.org/TR/html-aria/#dfn-no-corresponding-role">No corresponding role</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableColElement"><code>HTMLTableColElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`span`  
This attribute contains a positive integer indicating the number of consecutive columns the `<col>` element spans. If not present, its default value is `1`.

### Deprecated attributes

The following attributes are deprecated and should not be used. They are documented below for reference when updating existing code and for historical interest only.

 `align` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This enumerated attribute specifies how horizontal alignment of each column cell content will be handled. Possible values are:

-   `left`, aligning the content to the left of the cell
-   `center`, centering the content in the cell
-   `right`, aligning the content to the right of the cell
-   `justify`, inserting spaces into the textual content so that the content is justified in the cell

If this attribute is not set, its value is inherited from the [`align`](colgroup#attr-align) of the [`<colgroup>`](colgroup) element this `<col>` element belongs too. If there are none, the `left` value is assumed.

**Note:**
-   To achieve the same effect as the `left`, `center`, `right` or `justify` values:
    -   Do not try to set the [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) property on a selector giving a `<col>` element. Because [`<td>`](td) elements are not descendant of the `<col>` element, they won't inherit it.
    -   If the table doesn't use a [`colspan`](td#attr-colspan) attribute, use the `td:nth-child(an+b)` CSS selector. Set `a` to zero and `b `to the position of the column in the table, e.g. `td:nth-child(2) { text-align: right; }` to right-align the second column.
    -   If the table does use a [`colspan`](td#attr-colspan) attribute, the effect can be achieved by combining adequate CSS attribute selectors like `[colspan=n]`, though this is not trivial.

 `bgcolor` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The background color of the table. It is a [6-digit hexadecimal RGB code](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#rgb_colors), prefixed by a '`#`'. One of the predefined [color kewords](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#color_keywords) can also be used.

To achieve a similar effect, use the CSS [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) property.

 `char` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute is used to set the character to align the cells in a column on. Typical values for this include a period (.) when attempting to align numbers or monetary values. If [`align`](#attr-align) is not set to `char`, this attribute is ignored.

 `charoff` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute is used to indicate the number of characters to offset the column data from the alignment characters specified by the `char` attribute.

 `valign` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute specifies the vertical alignment of the text within each cell of the column. Possible values for this attribute are:

-   `baseline`, which will put the text as close to the bottom of the cell as it is possible, but align it on the [baseline](https://en.wikipedia.org/wiki/Baseline_%28typography%29) of the characters instead of the bottom of them. If characters are all of the size, this has the same effect as `bottom`.
-   `bottom`, which will put the text as close to the bottom of the cell as it is possible;
-   `middle`, which will center the text in the cell;
-   and `top`, which will put the text as close to the top of the cell as it is possible.

**Note:**
-   Do not try to set the [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align) property on a selector giving a `<col>` element. Because [`<td>`](td) elements are not descendant of the `<col>` element, they won't inherit it.
-   If the table doesn't use a [`colspan`](td#attr-colspan) attribute, use the `td:nth-child(an+b)` CSS selector where a is the total number of the columns in the table and b is the ordinal position of the column in the table. Only after this selector the `vertical-align` property can be used.
-   If the table does use a [`colspan`](td#attr-colspan) attribute, the effect can be achieved by combining adequate CSS attribute selectors like `[colspan=n]`, though this is not trivial.

 `width` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute specifies a default width for each column in the current column group. In addition to the standard pixel and percentage values, this attribute might take the special form `0*`, which means that the width of each column in the group should be the minimum width necessary to hold the column's contents. Relative widths such as `5*` also can be used.

Examples
--------

Please see the [`<table>`](table) page for examples on `<col>`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/tables.html#the-col-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;col&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/tabular-data.html#the-col-element">HTML5<br />
<span class="small">The definition of '&lt;col&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/tables.html#h-11.2.4.2">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;col&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`col`

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

`align`

?

12

No

See [bug 915](https://bugzil.la/915).

Yes

?

?

?

?

No

See [bug 915](https://bugzil.la/915).

?

?

?

`bgcolor`

?

?

No

Yes

?

?

?

?

No

?

?

?

`char`

?

12

No

See [bug 2212](https://bugzil.la/2212).

Yes

?

?

?

?

No

See [bug 2212](https://bugzil.la/2212).

?

?

?

`charoff`

?

12

No

See [bug 2212](https://bugzil.la/2212).

Yes

?

?

?

?

No

See [bug 2212](https://bugzil.la/2212).

?

?

?

`span`

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

`valign`

?

12

No

See [bug 915](https://bugzil.la/915).

Yes

?

?

?

?

No

See [bug 915](https://bugzil.la/915).

?

?

?

`width`

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

-   CSS properties and pseudo-classes that may be specially useful to style the `<col>` element:
    -   the [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) property to control the width of the column;
    -   the [`:nth-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child) pseudo-class to set the alignment on the cells of the column;
    -   the [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) property to align all cells content on the same character, like '.'.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/col</a>
