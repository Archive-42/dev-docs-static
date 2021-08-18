&lt;table&gt;: The Table element
================================

The `<table>` represents tabular data — that is, information presented in a two-dimensional table comprised of rows and columns of cells containing data.

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a></td></tr><tr class="even"><td>Permitted content</td><td><div class="content-models">In this order:<ol><li>an optional <a href="caption"><code>&lt;caption&gt;</code></a> element,</li><li>zero or more <a href="colgroup"><code>&lt;colgroup&gt;</code></a> elements,</li><li>an optional <a href="thead"><code>&lt;thead&gt;</code></a> element,</li><li>either one of the following:<ul><li>zero or more <a href="tbody"><code>&lt;tbody&gt;</code></a> elements</li><li>one or more <a href="tr"><code>&lt;tr&gt;</code></a> elements</li></ul></li><li>an optional <a href="tfoot"><code>&lt;tfoot&gt;</code></a> element</li></ol></div></td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts flow content</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><code>table</code></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>Any</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTableElement"><code>HTMLTableElement</code></a></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

### Deprecated attributes

 `align` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This enumerated attribute indicates how the table must be aligned inside the containing document. It may have the following values:

-   `left`: the table is displayed on the left side of the document;
-   `center`: the table is displayed in the center of the document;
-   `right`: the table is displayed on the right side of the document.

Set [`margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left) and [`margin-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right) to `auto` or [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) to `0 auto` to achieve an effect that is similar to the align attribute.

 `bgcolor` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The background color of the table. It is a [6-digit hexadecimal RGB code](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#rgb_colors), prefixed by a '`#`'. One of the predefined [color kewords](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#color_keywords) can also be used.

To achieve a similar effect, use the CSS [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) property.

 `border` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This integer attribute defines, in pixels, the size of the frame surrounding the table. If set to 0, the [`frame`](#attr-frame) attribute is set to void.

To achieve a similar effect, use the CSS [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) shorthand property.

 `cellpadding` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute defines the space between the content of a cell and its border, displayed or not. If the cellpadding's length is defined in pixels, this pixel-sized space will be applied to all four sides of the cell's content. If the length is defined using a percentage value, the content will be centered and the total vertical space (top and bottom) will represent this value. The same is true for the total horizontal space (left and right).

To achieve a similar effect, apply the [`border-collapse`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse) property to the `<table>` element, with its value set to collapse, and the [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) property to the [`<td>`](td) elements.

 `cellspacing` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute defines the size of the space between two cells in a percentage value or pixels. The attribute is applied both horizontally and vertically, to the space between the top of the table and the cells of the first row, the left of the table and the first column, the right of the table and the last column and the bottom of the table and the last row.

To achieve a similar effect, apply the [`border-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-spacing) property to the `<table>` element. `border-spacing` does not have any effect if [`border-collapse`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse) is set to collapse.

 `frame` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This enumerated attribute defines which side of the frame surrounding the table must be displayed.

To achieve a similar effect, use the [`border-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-style) and [`border-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-width) properties.

 `rules` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This enumerated attribute defines where rules, i.e. lines, should appear in a table. It can have the following values:

-   `none`, which indicates that no rules will be displayed; it is the default value;
-   `groups`, which will cause the rules to be displayed between row groups (defined by the [`<thead>`](thead), [`<tbody>`](tbody) and [`<tfoot>`](tfoot) elements) and between column groups (defined by the [`<col>`](col) and [`<colgroup>`](colgroup) elements) only;
-   `rows`, which will cause the rules to be displayed between rows;
-   `columns`, which will cause the rules to be displayed between columns;
-   `all`, which will cause the rules to be displayed between rows and columns.

To achieve a similar effect, apply the [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border) property to the appropriate [`<thead>`](thead), [`<tbody>`](tbody), [`<tfoot>`](tfoot), [`<col>`](col), or [`<colgroup>`](colgroup) elements.

 `summary` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute defines an alternative text that summarizes the content of the table. Use the [`<caption>`](caption) element instead.

 `width` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
This attribute defines the width of the table. Use the CSS [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) property instead.

Examples
--------

### Simple table

    <table>
      <tr>
        <td>John</td>
        <td>Doe</td>
      </tr>
      <tr>
        <td>Jane</td>
        <td>Doe</td>
      </tr>
    </table>

### Further simple examples

    <p>Simple table with header</p>
    <table>
      <tr>
        <th>First name</th>
        <th>Last name</th>
      </tr>
      <tr>
        <td>John</td>
        <td>Doe</td>
      </tr>
      <tr>
        <td>Jane</td>
        <td>Doe</td>
      </tr>
    </table>

    <p>Table with thead, tfoot, and tbody</p>
    <table>
      <thead>
        <tr>
          <th>Header content 1</th>
          <th>Header content 2</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Body content 1</td>
          <td>Body content 2</td>
        </tr>
      </tbody>
      <tfoot>
        <tr>
          <td>Footer content 1</td>
          <td>Footer content 2</td>
        </tr>
      </tfoot>
    </table>

    <p>Table with colgroup</p>
    <table>
      <colgroup span="4"></colgroup>
      <tr>
        <th>Countries</th>
        <th>Capitals</th>
        <th>Population</th>
        <th>Language</th>
      </tr>
      <tr>
        <td>USA</td>
        <td>Washington, D.C.</td>
        <td>309 million</td>
        <td>English</td>
      </tr>
      <tr>
        <td>Sweden</td>
        <td>Stockholm</td>
        <td>9 million</td>
        <td>Swedish</td>
      </tr>
    </table>

    <p>Table with colgroup and col</p>
    <table>
      <colgroup>
        <col style="background-color: #0f0">
        <col span="2">
      </colgroup>
      <tr>
        <th>Lime</th>
        <th>Lemon</th>
        <th>Orange</th>
      </tr>
      <tr>
        <td>Green</td>
        <td>Yellow</td>
        <td>Orange</td>
      </tr>
    </table>

    <p>Simple table with caption</p>
    <table>
      <caption>Awesome caption</caption>
      <tr>
        <td>Awesome data</td>
      </tr>
    </table>

Accessibility concerns
----------------------

### Captions

By supplying a [`<caption>`](caption) element whose value clearly and concisely describes the table's purpose, it helps the people decide if they need to read the rest of the table content or skip over it.

This helps people navigating with the aid of assistive technology such as a screen reader, people experiencing low vision conditions, and people with cognitive concerns.

-   [MDN Adding a caption to your table with &lt;caption&gt;](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Advanced#adding_a_caption_to_your_table_with_caption)
-   [Caption & Summary • Tables • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/tables/caption-summary/)

### Scoping rows and columns

The [`scope`](th#attr-scope) attribute on header elements is redundant in simple contexts, because scope is inferred. However, some assistive technologies may fail to draw correct inferences, so specifying header scope may improve user experiences. In complex tables, scope can be specified so as to provide necessary information about the cells related to a header.

#### Example

    <table>
      <caption>Color names and values</caption>
      <tbody>
        <tr>
          <th scope="col">Name</th>
          <th scope="col">HEX</th>
          <th scope="col">HSLa</th>
          <th scope="col">RGBa</th>
        </tr>
        <tr>
          <th scope="row">Teal</th>
          <td><code>#51F6F6</code></td>
          <td><code>hsla(180, 90%, 64%, 1)</code></td>
          <td><code>rgba(81, 246, 246, 1)</code></td>
        </tr>
        <tr>
          <th scope="row">Goldenrod</th>
          <td><code>#F6BC57</code></td>
          <td><code>hsla(38, 90%, 65%, 1)</code></td>
          <td><code>rgba(246, 188, 87, 1)</code></td>
        </tr>
      </tbody>
    </table>

Providing a declaration of `scope="col"` on a [`<th>`](th) element will help describe that the cell is at the top of a column. Providing a declaration of `scope="row"` on a [`<th>`](th) element will help describe that the cell is the first in a row.

-   [MDN Tables for visually impaired users](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Advanced#tables_for_visually_impaired_users)
-   [Tables with two headers • Tables • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/tables/two-headers/)
-   [Tables with irregular headers • Tables • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/tables/irregular/)
-   [H63: Using the scope attribute to associate header cells and data cells in data tables | W3C Techniques for WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/H63.html)

### Complicated tables

Assistive technology such as screen readers may have difficulty parsing tables that are so complex that header cells can’t be associated in a strictly horizontal or vertical way. This is typically indicated by the presence of the [`colspan`](td#attr-colspan) and [`rowspan`](td#attr-rowspan) attributes.

Ideally, consider alternate ways to present the table's content, including breaking it apart into a collection of smaller, related tables that don't have to rely on using the `colspan` and `rowspan` attributes. In addition to helping people who use assistive technology understand the table's content, this may also benefit people with cognitive concerns who may have difficulty understanding the associations the table layout is describing.

If the table cannot be broken apart, use a combination of the [`id`](../global_attributes#attr-id) and [`headers`](td#attr-headers) attributes to programmatically associate each table cell with the header(s) the cell is associated with.

-   [MDN Tables for visually impaired users](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Advanced#tables_for_visually_impaired_users)
-   [Tables with multi-level headers • Tables • W3C WAI Web Accessibility Tutorials](https://www.w3.org/WAI/tutorials/tables/multi-level/)
-   [H43: Using id and headers attributes to associate data cells with header cells in data tables | Techniques for W3C WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/H43.html)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/tables.html#the-table-element">HTML Living Standard<br />
<span class="small">The definition of 'table element' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/tabular-data.html#the-table-element">HTML5<br />
<span class="small">The definition of 'table element' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`table`

1

12

1

Yes

Yes

Yes

1

18

4

Yes

Yes

1.0

`align`

1

12

1

Yes

Yes

Yes

1

18

4

Yes

Yes

1.0

`bgcolor`

1

12

1

Yes

Yes

Yes

1

18

4

Yes

Yes

1.0

`border`

1

12

1

Yes

Yes

Yes

1

18

4

Yes

Yes

1.0

`cellpadding`

1

12

1

Yes

Yes

Yes

1

18

4

Yes

Yes

1.0

`cellspacing`

1

12

1

Yes

Yes

Yes

1

18

4

Yes

Yes

1.0

`frame`

1

12

1

Yes

Yes

Yes

1

18

4

Yes

Yes

1.0

`rules`

1

12

1

Yes

Yes

Yes

1

18

4

Yes

Yes

1.0

`summary`

1

12

1

Yes

Yes

Yes

1

18

4

Yes

Yes

1.0

`width`

1

12

1

Yes

Yes

Yes

1

18

4

Yes

Yes

1.0

See also
--------

-   CSS properties that may be especially useful to style the `<table>` element:
    -   [`width`](https://developer.mozilla.org/en-US/docs/Web/CSS/width) to control the width of the table;
    -   [`border`](https://developer.mozilla.org/en-US/docs/Web/CSS/border), [`border-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-style), [`border-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-color), [`border-width`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-width), [`border-collapse`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-collapse), [`border-spacing`](https://developer.mozilla.org/en-US/docs/Web/CSS/border-spacing) to control the aspect of cell borders, rules and frame;
    -   [`margin`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin) and [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding) to style the individual cell content;
    -   [`text-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/text-align) and [`vertical-align`](https://developer.mozilla.org/en-US/docs/Web/CSS/vertical-align) to define the alignment of text and cell content.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table</a>
