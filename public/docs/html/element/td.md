&lt;td&gt;: The Table Data Cell element
=======================================

The `<td>` defines a cell of a table that contains data. It participates in the *table model*.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>Sectioning root.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>The start tag is mandatory.<br />
The end tag may be omitted, if it is immediately followed by a <a href="th"><code>&lt;th&gt;</code></a> or <a href="td"><code>&lt;td&gt;</code></a> element or if there are no more data in its parent element.</td></tr><tr class="even"><td>Permitted parents</td><td>A <a href="tr"><code>&lt;tr&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>cell</code> if a descendant of a <a href="table"><code>&lt;table&gt;</code></a> element</td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableCellElement"><code>HTMLTableCellElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

`colspan`  
This attribute contains a non-negative integer value that indicates for how many columns the cell extends. Its default value is `1`. Values higher than 1000 will be considered as incorrect and will be set to the default value (1).

`headers`  
This attribute contains a list of space-separated strings, each corresponding to the **id** attribute of the [`<th>`](th) elements that apply to this element.

`rowspan`  
This attribute contains a non-negative integer value that indicates for how many rows the cell extends. Its default value is `1`; if its value is set to `0`, it extends until the end of the table section ([`<thead>`](thead), [`<tbody>`](tbody), [`<tfoot>`](tfoot), even if implicitly defined), that the cell belongs to. Values higher than 65534 are clipped down to 65534.

### Deprecated attributes

 `abbr` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute contains a short abbreviated description of the cell's content. Some user-agents, such as speech readers, may present this description before the content itself.

**Note:** Do not use this attribute as it is obsolete in the latest standard. Alternatively, you can put the abbreviated description inside the cell and place the long content in the **title** attribute.

 `align` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This enumerated attribute specifies how the cell content's horizontal alignment will be handled. Possible values are:

-   `left`: The content is aligned to the left of the cell.
-   `center`: The content is centered in the cell.
-   `right`: The content is aligned to the right of the cell.
-   `justify` (with text only): The content is stretched out inside the cell so that it covers its entire width.
-   `char` (with text only): The content is aligned to a character inside the `<th>` element with minimal offset. This character is defined by the [`char`](#attr-char) and [`charoff`](#attr-charoff) attributes <span class="notecard inline warning">Unimplemented (see [bug 2212](https://bugzilla.mozilla.org/show_bug.cgi?id=2212))</span>.

The default value when this attribute is not specified is `left`.

**Note:**
-   To achieve the same effect as the `left`, `center`, `right` or `justify` values, apply the CSS [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) property to the element.
-   To achieve the same effect as the `char` value, give the [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) property the same value you would use for the [`char`](#attr-char). <span class="notecard inline warning">Unimplemented</span> in CSS3.

 `axis` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute contains a list of space-separated strings. Each string is the `id` of a group of cells that this header applies to.

 `bgcolor` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute defines the background color of each cell in a column. It is a [6-digit hexadecimal RGB code](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#rgb_colors), prefixed by a '`#`'. One of the predefined [color kewords](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#color_keywords) can also be used.

To achieve a similar effect, use the CSS [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) property.

 `char` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The content in the cell element is aligned to a character. Typical values include a period (.) to align numbers or monetary values. If [`align`](#attr-align) is not set to `char`, this attribute is ignored.

 `charoff` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute is used to shift column data to the right of the character specified by the **char** attribute. Its value specifies the length of this shift.

 `height` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute is used to define a recommended cell height. Use the CSS [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height) property instead.

 `scope` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This enumerated attribute defines the cells that the header (defined in the [`<th>`](th)) element relates to. Only use this attribute with the `<th>` element to define the row or column for which it is a header.

 `valign` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute specifies how a text is vertically aligned inside a cell. Possible values for this attribute are:

-   `baseline`: Positions the text near the bottom of the cell and aligns it with the [baseline](https://en.wikipedia.org/wiki/Baseline_%28typography%29) of the characters instead of the bottom. If characters don't descend below the baseline, the baseline value achieves the same effect as `bottom`.
-   `bottom`: Positions the text near the bottom of the cell.
-   `middle`: Centers the text in the cell.
-   and `top`: Positions the text near the top of the cell.

To achieve a similar effect, use the CSS [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align) property.

 `width` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute is used to define a recommended cell width. Use the CSS [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) property instead.

Examples
--------

See [`<table>`](table) for examples on `<td>`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/tables.html#the-td-element">HTML Living Standard<br />
<span class="small">The definition of 'td element' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/tabular-data.html#the-td-element">HTML5<br />
<span class="small">The definition of 'td element' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`td`

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

`abbr`

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

See [bug 915](https://bugzil.la/915)

Yes

?

?

?

?

No

See [bug 915](https://bugzil.la/915)

?

?

?

`axis`

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

See [bug 2212](https://bugzil.la/2212)

Yes

?

?

?

?

No

See [bug 2212](https://bugzil.la/2212)

?

?

?

`charoff`

?

12

No

See [bug 2212](https://bugzil.la/2212)

Yes

?

?

?

?

No

See [bug 2212](https://bugzil.la/2212)

?

?

?

`colspan`

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

`headers`

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

`rowspan`

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

`scope`

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

See [bug 915](https://bugzil.la/915)

Yes

?

?

?

?

No

See [bug 915](https://bugzil.la/915)

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

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/td</a>
