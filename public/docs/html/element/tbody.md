&lt;tbody&gt;: The Table Body element
=====================================

The **HTML Table Body element** (`<tbody>`) encapsulates a set of table rows ([`<tr>`](tr) elements), indicating that they comprise the body of the table ([`<table>`](table)).

The `<tbody>` element, along with its cousins [`<thead>`](thead) and [`<tfoot>`](tfoot), provide useful semantic information that can be used when rendering for either screen or printer as well as for [accessibility](https://developer.mozilla.org/en-US/docs/Glossary/Accessibility) purposes.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td>None.</td></tr><tr class="even"><td>Permitted content</td><td>Zero or more <a href="tr"><code>&lt;tr&gt;</code></a> elements.</td></tr><tr class="odd"><td>Tag omission</td><td>The <code>&lt;tbody&gt;</code> element is not a required child element for a parent <a href="table"><code>&lt;table&gt;</code></a> element to graphically render. However, it must not be present, if its parent <a href="table"><code>&lt;table&gt;</code></a> element has a <a href="tr"><code>&lt;tr&gt;</code></a> element as a child.</td></tr><tr class="even"><td>Permitted parents</td><td>Within the required parent <a href="table"><code>&lt;table&gt;</code></a> element, the <code>&lt;tbody&gt;</code> element can be added after a <a href="caption"><code>&lt;caption&gt;</code></a>, <a href="colgroup"><code>&lt;colgroup&gt;</code></a>, and a <a href="thead"><code>&lt;thead&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>rowgroup</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableSectionElement"><code>HTMLTableSectionElement</code></a></td></tr></tbody></table>

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
-   `char`, aligning the textual content on a special character with a minimal offset, defined by the [`char`](#attr-char) and [`charoff`](#attr-charoff) attributes.

If this attribute is not set, the `left` value is assumed.

As this attribute is deprecated, use the CSS [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) property instead.

**Note:** The equivalent `text-align` property for the `align="char"` is not implemented in any browsers yet. See the [`text-align`'s browser compatibility section](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align#browser_compatibility) for the `<string>` value.

 `bgcolor` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The background color of the table. It is a [6-digit hexadecimal RGB code](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#rgb_colors), prefixed by a '`#`'. One of the predefined [color kewords](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#color_keywords) can also be used.

As this attribute is deprecated, use the CSS [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) property instead.

 `char` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute is used to set the character to align the cells in a column on. Typical values for this include a period (`.`) when attempting to align numbers or monetary values. If [`align`](#attr-align) is not set to `char`, this attribute is ignored.

 `charoff` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute is used to indicate the number of characters to offset the column data from the alignment characters specified by the `char` attribute.

 `valign` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute specifies the vertical alignment of the text within each row of cells of the table header. Possible values for this attribute are:

-   `baseline`, which will put the text as close to the bottom of the cell as it is possible, but align it on the [baseline](https://en.wikipedia.org/wiki/Baseline_%28typography%29) of the characters instead of the bottom of them. If characters are all of the size, this has the same effect as `bottom`.
-   `bottom`, which will put the text as close to the bottom of the cell as it is possible;
-   `middle`, which will center the text in the cell;
-   and `top`, which will put the text as close to the top of the cell as it is possible.

As this attribute is deprecated, use the CSS [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align) property instead.

Usage notes
-----------

-   If the table includes a [`<thead>`](thead) block (to semantically identify header rows), the `<tbody>` block *must* come after it.
-   If you use `<tbody>`, you can't also have table rows ([`<tr>`](tr) elements) which are direct children of the [`<table>`](table) but not included inside the `<tbody>`. All non-header and non-footer rows must be inside the `<tbody>` if one is used.
-   When printing a document, the `<thead>` and [`<tfoot>`](tfoot) elements specify information that may be the same—or at least very similar—on every page of a multi-page table, while the `<tbody>` element's contents generally will differ from page to page.
-   When a table is presented in a screen context (such as a window) which is not large enough to display the entire table, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) may let the user scroll the contents of the `<thead>`, `<tbody>`, `<tfoot>`, and [`<caption>`](caption) blocks separately from one another for the same parent table.
-   You *may* use more than one `<tbody>` per table as long as they are all consecutive. This lets you divide the rows in large tables into sections, each of which may be separately formatted if so desired.

Examples
--------

Below are some examples showing the use of the `<tbody>` element. For more examples of this tag in use, see the examples for [`<table>`](table#examples).

### Basic example

In this relatively simple example, we create a table listing information about a group of students with a [`<thead>`](thead) and a [`<tbody>`](tbody), with a number of rows in the body.

#### HTML

The table's HTML is shown here. Note that all of the body cells including information about students are contained within a single `<tbody>` element.

    <table>
      <thead>
        <tr>
          <th>Student ID</th>
          <th>Name</th>
          <th>Major</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>3741255</td>
          <td>Jones, Martha</td>
          <td>Computer Science</td>
        </tr>
        <tr>
          <td>3971244</td>
          <td>Nim, Victor</td>
          <td>Russian Literature</td>
        </tr>
        <tr>
          <td>4100332</td>
          <td>Petrov, Alexandra</td>
          <td>Astrophysics</td>
        </tr>
      </tbody>
    </table>

#### CSS

The CSS to style our table is shown next.

    table {
      border: 2px solid #555;
      border-collapse: collapse;
      font: 16px "Lucida Grande", "Helvetica", "Arial", sans-serif;
    }

First, the table's overall style attributes are set, configuring the thickness, style, and color of the table's exterior borders and using [`border-collapse`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse) to ensure that the border lines are shared among adjacent cells rather than each having its own borders with space in between. [`font`](https://developer.mozilla.org/en-US/docs/Web/CSS/font) is used to establish an initial font for the table.

    th, td {
      border: 1px solid #bbb;
      padding: 2px 8px 0;
      text-align: left;
    }

Then the style is set for the majority of the cells in the table, including all data cells but also those styles shared between our [`<td>`](td) and [`<th>`](th) cells. The cells are given a light gray outline which is a single pixel thick, padding is adjusted, and all cells are left-aligned using [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align)

    thead > tr > th {
      background-color: #cce;
      font-size: 18px;
      border-bottom: 2px solid #999;
    }

Finally, header cells contained within the [`<thead>`](thead) block are given additional styling. They use a darker [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color), a larger font size, and a thicker, darker bottom border than the other cell borders.

#### Result

The resulting table looks like this:

### Multiple bodies

You can create multiple sections within a table by using multiple `<tbody>` elements. Each may potentially have its own header row or rows; however, *there can be only one [`<thead>`](thead) per table!* Because of that, you need to use a [`<tr>`](tr) filled with [`<th>`](th) elements to create headers within each `<tbody>`. Let's see how that's done.

Let's take the previous example, add some more students to the list, and update the table so that instead of listing each student's major on every row, the students are grouped by major, with heading rows for each major.

#### Result

First, the resulting table, so you know what we're building:

#### HTML

The revised HTML looks like this:

    <table>
      <thead>
        <tr>
          <th>Student ID</th>
          <th>Name</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <th colspan="2">Computer Science</th>
        </tr>
        <tr>
          <td>3741255</td>
          <td>Jones, Martha</td>
        </tr>
        <tr>
          <td>4077830</td>
          <td>Pierce, Benjamin</td>
        </tr>
        <tr>
          <td>5151701</td>
          <td>Kirk, James</td>
        </tr>
      </tbody>
      <tbody>
        <tr>
          <th colspan="2">Russian Literature</th>
        </tr>
        <tr>
          <td>3971244</td>
          <td>Nim, Victor</td>
        </tr>
      </tbody>
      <tbody>
        <tr>
          <th colspan="2">Astrophysics</th>
        </tr>
        <tr>
          <td>4100332</td>
          <td>Petrov, Alexandra</td>
        </tr>
        <tr>
          <td>8892377</td>
          <td>Toyota, Hiroko</td>
        </tr>
      </tbody>
    </table>

Notice that each major is placed in a separate `<tbody>` block, the first row of which contains a single [`<th>`](th) element with a [`colspan`](th#attr-colspan) attribute that spans the entire width of the table. That heading lists the name of the major contained within the `<tbody>`.

Then each remaining row in each major's `<tbody>` consists of two cells: the first for the student's ID and the second for their name.

#### CSS

Most of the CSS is unchanged. We do, however, add a slightly more subtle style for header cells contained directly within a `<tbody>` (as opposed to those which reside in a [`<thead>`](thead)). This is used for the headers indicating each table section's corresponding major.

    tbody > tr > th {
      background-color: #dde;
      border-bottom: 1.5px solid #bbb;
      font-weight: normal;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/tables.html#the-tbody-element">HTML Living Standard<br />
<span class="small">The definition of 'tbody element' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/tabular-data.html#the-tbody-element">HTML5<br />
<span class="small">The definition of 'tbody element' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`tbody`

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

-   CSS properties and [pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) that may be specially useful to style the `<tbody>` element:
    -   the [`:nth-child`](https://developer.mozilla.org/en-US/docs/Web/CSS/:nth-child) pseudo-class to set the alignment on the cells of the column;
    -   the [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) property to align all cells content on the same character, like '.'.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/tbody</a>
