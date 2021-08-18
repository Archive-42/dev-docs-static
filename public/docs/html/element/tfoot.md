&lt;tfoot&gt;: The Table Foot element
=====================================

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td>Zero or more <a href="tr"><code>&lt;tr&gt;</code></a> elements.</td></tr><tr class="odd"><td>Tag omission</td><td>The start tag is mandatory. The end tag may be omitted if there is no more content in the parent <a href="table"><code>&lt;table&gt;</code></a> element.</td></tr><tr class="even"><td>Permitted parents</td><td>A <a href="table"><code>&lt;table&gt;</code></a> element. The <a href="tfoot"><code>&lt;tfoot&gt;</code></a> must appear after any <a href="caption"><code>&lt;caption&gt;</code></a>, <a href="colgroup"><code>&lt;colgroup&gt;</code></a>, <a href="thead"><code>&lt;thead&gt;</code></a>, <a href="tbody"><code>&lt;tbody&gt;</code></a>, or <a href="tr"><code>&lt;tr&gt;</code></a> element. Note that this is the requirement as of HTML5.<br />
In HTML4, the <a href="tfoot"><code>&lt;tfoot&gt;</code></a> element cannot be placed after any <a href="tbody"><code>&lt;tbody&gt;</code></a> and <a href="tr"><code>&lt;tr&gt;</code></a> element. Note that this directly contradicts the above normative requirement from HTML5.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>rowgroup</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableSectionElement"><code>HTMLTableSectionElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

### Deprecated attributes

The following attributes are deprecated and should not be used. They are documented below for reference when updating existing code and for historical interest only.

 `align` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This enumerated attribute specifies how horizontal alignment of each cell content will be handled. Possible values are:

-   `left`, aligning the content to the left of the cell
-   `center`, centering the content in the cell
-   `right`, aligning the content to the right of the cell
-   `justify`, inserting spaces into the textual content so that the content is justified in the cell
-   `char`, aligning the textual content on a special character with a minimal offset, defined by the [`char`](tbody#attr-char) and [`charoff`](tbody#attr-charoff) attributes.

If this attribute is not set, the `left` value is assumed.

**Note:**
-   To achieve the same effect as the `left`, `center`, `right` or `justify` values, use the CSS [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) property on it.
-   To achieve the same effect as the `char` value, in CSS3, you can use the value of the [`char`](#attr-char) as the value of the [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) property <span class="notecard inline warning">Unimplemented</span>.

 `bgcolor` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The background color of the table. It is a [6-digit hexadecimal RGB code](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#rgb_colors), prefixed by a '`#`'. One of the predefined [color kewords](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#color_keywords) can also be used.

To achieve a similar effect, use the CSS [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) property.

 `char` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute specifies the alignment of the content in a column to a character. Typical values for this include a period (.) when attempting to align numbers or monetary values. If [`align`](#attr-align) is not set to `char`, this attribute is ignored.

 `charoff` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute is used to indicate the number of characters to offset the column data from the alignment characters specified by the `char` attribute.

 `valign` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute specifies the vertical alignment of the text within each row of cells of the table footer. Possible values for this attribute are:

-   `baseline`, which will put the text as close to the bottom of the cell as it is possible, but align it on the [baseline](https://en.wikipedia.org/wiki/Baseline_%28typography%29) of the characters instead of the bottom of them. If characters are all of the size, this has the same effect as `bottom`.
-   `bottom`, which will put the text as close to the bottom of the cell as it is possible;
-   `middle`, which will center the text in the cell;
-   and `top`, which will put the text as close to the top of the cell as it is possible.

**Note:** Do not use this attribute as it is obsolete (and not supported) in the latest standard: instead set the CSS [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align) property on it.

Examples
--------

Please see the [`<table>`](table) page for examples on `<tfoot>`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/tables.html#the-tfoot-element">HTML Living Standard<br />
<span class="small">The definition of 'tfoot element' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/tabular-data.html#the-tfoot-element">HTML5<br />
<span class="small">The definition of 'tfoot element' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`tfoot`

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

See also
--------

-   Other table-related HTML Elements: [`<caption>`](caption), [`<col>`](col), [`<colgroup>`](colgroup), [`<table>`](table), [`<tbody>`](tbody), [`<td>`](td), [`<th>`](th), [`<thead>`](thead), [`<tr>`](tr);
-   CSS properties and pseudo-classes that may be specially useful to style the `<tfoot>` element:
    -   the [`:nth-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child) pseudo-class to set the alignment on the cells of the column;
    -   the [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) property to align all cells content on the same character, like '.'.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tfoot</a>
