&lt;thead&gt;: The Table Head element
=====================================

The `<thead>` defines a set of rows defining the head of the columns of the table.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td>Zero or more <a href="tr"><code>&lt;tr&gt;</code></a> elements.</td></tr><tr class="odd"><td>Tag omission</td><td>The start tag is mandatory. The end tag may be omitted if the <a href="thead"><code>&lt;thead&gt;</code></a> element is immediately followed by a <a href="tbody"><code>&lt;tbody&gt;</code></a> or <a href="tfoot"><code>&lt;tfoot&gt;</code></a> element.</td></tr><tr class="even"><td>Permitted parents</td><td>A <a href="table"><code>&lt;table&gt;</code></a> element. The <a href="thead"><code>&lt;thead&gt;</code></a> must appear after any <a href="caption"><code>&lt;caption&gt;</code></a> or <a href="colgroup"><code>&lt;colgroup&gt;</code></a> element, even implicitly defined, but before any <a href="tbody"><code>&lt;tbody&gt;</code></a>, <a href="tfoot"><code>&lt;tfoot&gt;</code></a> and <a href="tr"><code>&lt;tr&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>rowgroup</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableSectionElement"><code>HTMLTableSectionElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

### Deprecated attributes

 `align` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This enumerated attribute specifies how horizontal alignment of each cell content will be handled. Possible values are:

-   `left`, aligning the content to the left of the cell
-   `center`, centering the content in the cell
-   `right`, aligning the content to the right of the cell
-   `justify`, inserting spaces into the textual content so that the content is justified in the cell
-   `char`, aligning the textual content on a special character with a minimal offset, defined by the [`char`](#attr-char) and [`charoff`](#attr-charoff) attributes <span class="notecard inline warning">Unimplemented (see [bug 2212](https://bugzilla.mozilla.org/show_bug.cgi?id=2212))</span>.

If this attribute is not set, the `left` value is assumed.

**Note:** Do not use this attribute as it is obsolete (not supported) in the latest standard.
-   To achieve the same effect as the `left`, `center`, `right` or `justify` values, use the CSS [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) property on it.
-   To achieve the same effect as the `char` value, in CSS3, you can use the value of the [`char`](#attr-char) as the value of the [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) property <span class="notecard inline warning">Unimplemented</span>.

 `bgcolor` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
This attribute defines the background color of each cell of the column. It is one of the 6-digit hexadecimal code as defined in [sRGB](https://www.w3.org/Graphics/Color/sRGB), prefixed by a '\#'. One of the sixteen predefined color strings may be used:

<table><tbody><tr class="odd"><td></td><td><code>black</code> = "#000000"</td><td></td><td><code>green</code> = "#008000"</td></tr><tr class="even"><td></td><td><code>silver</code> = "#C0C0C0"</td><td></td><td><code>lime</code> = "#00FF00"</td></tr><tr class="odd"><td></td><td><code>gray</code> = "#808080"</td><td></td><td><code>olive</code> = "#808000"</td></tr><tr class="even"><td></td><td><code>white</code> = "#FFFFFF"</td><td></td><td><code>yellow</code> = "#FFFF00"</td></tr><tr class="odd"><td></td><td><code>maroon</code> = "#800000"</td><td></td><td><code>navy</code> = "#000080"</td></tr><tr class="even"><td></td><td><code>red</code> = "#FF0000"</td><td></td><td><code>blue</code> = "#0000FF"</td></tr><tr class="odd"><td></td><td><code>purple</code> = "#800080"</td><td></td><td><code>teal</code> = "#008080"</td></tr><tr class="even"><td></td><td><code>fuchsia</code> = "#FF00FF"</td><td></td><td><code>aqua</code> = "#00FFFF"</td></tr></tbody></table>

**Usage note:** Do not use this attribute, as it is non-standard and only implemented in some versions of Microsoft Internet Explorer: the [`<thead>`](thead) element should be styled using [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS). To give a similar effect to the **bgcolor** attribute, use the [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color), on the relevant [`<td>`](td) or [`<th>`](th) elements.

 `char` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute is used to set the character to align the cells in a column on. Typical values for this include a period (.) when attempting to align numbers or monetary values. If [`align`](#attr-align) is not set to `char`, this attribute is ignored.

**Note:** Do not use this attribute as it is obsolete (and not supported) in the latest standard. To achieve the same effect as the [`char`](#attr-char), in CSS3, you can use the character set using the [`char`](#attr-char) attribute as the value of the [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) property <span class="notecard inline warning">Unimplemented</span>.

 `charoff` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute is used to indicate the number of characters to offset the column data from the alignment characters specified by the **char** attribute.

**Note:** Do not use this attribute as it is obsolete (and not supported) in the latest standard.

 `valign` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute specifies the vertical alignment of the text within each row of cells of the table header. Possible values for this attribute are:

-   `baseline`, which will put the text as close to the bottom of the cell as it is possible, but align it on the [baseline](https://en.wikipedia.org/wiki/Baseline_%28typography%29) of the characters instead of the bottom of them. If characters are all of the size, this has the same effect as `bottom`.
-   `bottom`, which will put the text as close to the bottom of the cell as it is possible;
-   `middle`, which will center the text in the cell;
-   `top`, which will put the text as close to the top of the cell as it is possible.

**Note:** Do not use this attribute as it is obsolete (and not supported) in the latest standard: instead set the CSS [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align) property on it.

Examples
--------

See [`<table>`](table) for examples on `<thead>`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/tables.html#the-thead-element">HTML Living Standard<br />
<span class="small">The definition of 'thead element' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/tabular-data.html#the-thead-element">HTML5<br />
<span class="small">The definition of 'thead element' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`thead`

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

-   Other table-related HTML Elements: [`<caption>`](caption), [`<col>`](col), [`<colgroup>`](colgroup), [`<table>`](table), [`<tbody>`](tbody), [`<td>`](td), [`<tfoot>`](tfoot), [`<th>`](th), [`<tr>`](tr);
-   CSS properties and pseudo-classes that may be specially useful to style the `<thead>` element:
    -   the [`:nth-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child) pseudo-class to set the alignment on the cells of the column;
    -   the [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) property to align all cells content on the same character, like '.'.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/thead</a>
