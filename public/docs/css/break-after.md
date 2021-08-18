# break-after

The `break-after` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how page, column, or region breaks should behave after a generated box. If there is no generated box, the property is ignored.

    /* Generic break values */
    break-after: auto;
    break-after: avoid;
    break-after: always;
    break-after: all;

    /* Page break values */
    break-after: avoid-page;
    break-after: page;
    break-after: left;
    break-after: right;
    break-after: recto;
    break-after: verso;

    /* Column break values */
    break-after: avoid-column;
    break-after: column;

    /* Region break values */
    break-after: avoid-region;
    break-after: region;

    /* Global values */
    break-after: inherit;
    break-after: initial;
    break-after: unset;

Each possible break point (in other words, each element boundary) is affected by three properties: the `break-after` value of the previous element, the [`break-before`](break-before) value of the next element, and the [`break-inside`](break-inside) value of the containing element.

To determine if a break must be done, the following rules are applied:

1.  If any of the three concerned values is a _forced break value_ (`always`, `left`, `right`, `page`, `column`, or `region`), it has precedence. If more than one of them are such a break, the one of the element that appears the latest in the flow is taken (i.e., the `break-before` value has precedence over the `break-after` value, which itself has precedence over the `break-inside` value).
2.  If any of the three concerned values is an _avoid break value_ (`avoid`, `avoid-page`, `avoid-region`, or `avoid-column`), no such break will be applied at that point.

Once forced breaks have been applied, soft breaks may be added if needed, but not on element boundaries that resolve in a corresponding `avoid` value.

## Syntax

The `break-after` property is specified as one of the keyword values from the list below.

### Values

#### Generic break values

`auto`  
Allows, but does not force, any break (page, column, or region) to be inserted right after the principal box.

`avoid`  
Avoids any break (page, column, or region) from being inserted right after the principal box.

`always` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Forces a page break right after the principal box. The type of this break is that of the immediately-containing fragmentation context. If we are inside a multicol container then it would force a column break, inside paged media (but not inside a multicol container) a page break.

`all` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Forces a page break right after the principal box. Breaking through all possible fragmentation contexts. So a break inside a multicol container, which was inside a page container would force a column and page break.

#### Page break values

`avoid-page`  
Avoids any page break right after the principal box.

`page`  
Forces a page break right after the principal box.

`left`  
Forces one or two page breaks right after the principal box, whichever will make the next page into a left page.

`right`  
Forces one or two page breaks right after the principal box, whichever will make the next page into a right page.

`recto` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Forces one or two page breaks right after the principal box, whichever will make the next page into a recto page. (A recto page is a right page in a left-to-right spread or a left page in a right-to-left spread.)

`verso` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Forces one or two page breaks right after the principal box, whichever will make the next page into a verso page. (A verso page is a left page in a left-to-right spread or a right page in a right-to-left spread.)

#### Column break values

`avoid-column`  
Avoids any column break right after the principal box.

`column`  
Forces a column break right after the principal box.

#### Region break values

`avoid-region` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Avoids any region break right after the principal box.

`region` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Forces a region break right after the principal box.

## Page break aliases

For compatibility reasons, the legacy [`page-break-after`](page-break-after) property should be treated by browsers as an alias of `break-after`. This ensures that sites using `page-break-after` continue to work as designed. A subset of values should be aliased as follows:

<table><thead><tr class="header"><th>page-break-after</th><th>break-after</th></tr></thead><tbody><tr class="odd"><td><code>auto</code></td><td><code>auto</code></td></tr><tr class="even"><td><code>left</code></td><td><code>left</code></td></tr><tr class="odd"><td><code>right</code></td><td><code>right</code></td></tr><tr class="even"><td><code>avoid</code></td><td><code>avoid</code></td></tr><tr class="odd"><td><code>always</code></td><td><code>page</code></td></tr></tbody></table>

The `always` value of `page-break-*` was implemented by browsers as a page break, and not as a column break. Therefore the aliasing is to `page`, rather than the `always` value in the Level 4 spec.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>block-level elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | avoid | always | all | avoid-page | page | left | right | recto | verso | avoid-column | column | avoid-region | region

## Examples

### Breaking into neat columns

In the following example we have a container that contains an `<h1>` spanning all columns (achieved using `column-span: all`) and a series of `<h2>`s and paragraphs laid out in multiple columns using `column-width: 200px`.

By default, the subheadings and paragraphs were laid out rather messily because the headings were not in a uniform place. However, we used `break-after: column` on the `<p>` elements to force a column break after each one, meaning that you end up with an `<h2>` neatly at the top of each column.

#### HTML

    <article>
      <h1>Main heading</h1>

      <h2>Subheading</h2>

      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla vitae fringilla mauris. Quisque commodo eget nisi sed pretium. Mauris luctus nec lacus in ultricies. Mauris vitae hendrerit arcu, ac scelerisque lacus. Aliquam lobortis in lacus sit amet posuere. Fusce iaculis urna id neque dapibus, eu lacinia lectus dictum.</p>

      <h2>Subheading</h2>

      <p>Praesent condimentum dui dui, sit amet rutrum diam tincidunt eu. Cras suscipit porta leo sit amet rutrum. Sed vehicula ornare tincidunt. Curabitur a ipsum ac diam mattis volutpat ac ut elit. Nullam luctus justo non vestibulum gravida. Morbi metus libero, pharetra non porttitor a, molestie nec nisi.</p>

      <h2>Subheading</h2>

      <p>Vivamus eleifend metus vitae neque placerat, eget interdum elit mattis. Donec eu vulputate nibh. Ut turpis leo, malesuada quis nisl nec, volutpat egestas tellus.

      <h2>Subheading</h2>

      <p>In finibus viverra enim vel suscipit. Quisque consequat velit eu orci malesuada, ut interdum tortor molestie. Proin sed pellentesque augue. Nam risus justo, faucibus non porta a, congue vel massa. Cras luctus lacus nisl, sed tincidunt velit pharetra ac. Duis suscipit faucibus dui sed ultricies.</p>
    </article>

#### CSS

    html {
      font-family: helvetica, arial, sans-serif;
    }

    h1 {
      font-size: 3rem;
      letter-spacing: 2px;
      column-span: all;
    }

    h2 {
      font-size: 1.2rem;
      color: red;
      letter-spacing: 1px;
    }

    p {
      line-height: 1.5;
      break-after: column;
    }

    article {
      column-width: 200px;
      gap: 20px;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-break-3/#break-between">CSS Fragmentation Module Level 3<br />
<span class="small">The definition of 'break-after' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds the <code>recto</code> and <code>verso</code> keywords. Changes the media type of this property from <code>paged</code> to <a href="@media"><code>visual</code></a>. Defines the breaking algorithm with different kinds of breaks.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-regions-1/#region-flow-break">CSS Regions Module Level 1<br />
<span class="small">The definition of 'break-after' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Extends the property to handle region breaks. Adds the <code>avoid-region</code> and <code>region</code> keywords.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-multicol-1/#break-before-break-after-break-inside">CSS Multi-column Layout Module<br />
<span class="small">The definition of 'break-after' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition. Extends the CSS 2.1 <a href="page-break-after"><code>page-break-after</code></a> property to handle both page and column breaks.</td></tr></tbody></table>

## Browser compatibility

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

`break-after`

50

12

65

10

37

11.1-12.1

10

50

50

65

37

11.1-12.1

10

5.0

`always`

No

12-79

65

10

11.1-12.1

No

50

No

65

No

No

No

`page`

50

12

65

10

11.1-12.1

10

50

50

65

37

10

5.0

`recto`

No

See [bug 538475](https://crbug.com/538475).

No

No

No

No

No

No

No

No

No

No

No

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

`break-after`

50

12

65

Only supported in print mode. See [bug 1675322](https://bugzil.la/1675322).

10

37

11.1-12.1

No

50

50

65

Only supported in print mode. See [bug 1675322](https://bugzil.la/1675322).

37

11.1-12.1

No

5.0

`always`

No

No

65

Only supported in print mode. See [bug 1675322](https://bugzil.la/1675322).

No

No

No

No

No

65

Only supported in print mode. See [bug 1675322](https://bugzil.la/1675322).

No

No

No

`avoid-column`

No

12-79

No

No

No

No

No

No

No

No

No

No

`column`

50

12

No

10

11.1-15

37

No

50

50

No

11.1-14

37

No

5.0

BCD tables only load in the browser

### Support in paged media

BCD tables only load in the browser

## See also

- [Multiple-column Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout)
- [Breaking Boxes With CSS Fragmentation](https://www.smashingmagazine.com/2019/02/css-fragmentation/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/break-after" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/break-after</a>
