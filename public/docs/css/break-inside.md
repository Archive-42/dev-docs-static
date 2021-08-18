# break-inside

The `break-inside` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how page, column, or region breaks should behave inside a generated box. If there is no generated box, the property is ignored.

    /* Keyword values */
    break-inside: auto;
    break-inside: avoid;
    break-inside: avoid-page;
    break-inside: avoid-column;
    break-inside: avoid-region;

    /* Global values */
    break-inside: inherit;
    break-inside: initial;
    break-inside: unset;

Each possible break point (in other words, each element boundary) is affected by three properties: the [`break-after`](break-after) value of the previous element, the [`break-before`](break-before) value of the next element, and the `break-inside` value of the containing element.

To determine if a break must be done, the following rules are applied:

1.  If any of the three concerned values is a _forced break value_ (`always`, `left`, `right`, `page`, `column`, or `region`), it has precedence. If more than one of them are such a break, the value of the element that appears the latest in the flow is used. Thus, the `break-before` value has precedence over the `break-after` value, which in turn has precedence over the `break-inside` value.
2.  If any of the three concerned values is an _avoid break value_ (`avoid`, `avoid-page`, `avoid-region`, or `avoid-column`), no such break will be applied at that point.

Once forced breaks have been applied, soft breaks may be added if needed, but not on element boundaries that resolve in a corresponding `avoid` value.

## Syntax

The `break-inside` property is specified as one of the keyword values from the list below.

### Values

`auto`  
Allows, but does not force, any break (page, column, or region) to be inserted within the principal box.

`avoid`  
Avoids any break (page, column, or region) from being inserted within the principal box.

`avoid-page`  
Avoids any page break within the principal box.

`avoid-column`  
Avoids any column break within the principal box.

`avoid-region` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Avoids any region break within the principal box.

## Page break aliases

For compatibility reasons, the legacy [`page-break-inside`](page-break-inside) property should be treated by browsers as an alias of `break-inside`. This ensures that sites using `page-break-inside` continue to work as designed. A subset of values should be aliased as follows:

<table><thead><tr class="header"><th>page-break-inside</th><th>break-inside</th></tr></thead><tbody><tr class="odd"><td><code>auto</code></td><td><code>auto</code></td></tr><tr class="even"><td><code>avoid</code></td><td><code>avoid</code></td></tr></tbody></table>

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>block-level elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | avoid | avoid-page | avoid-column | avoid-region

## Examples

### Avoiding breaking inside a figure

In the following example we have a container that contains an `<h1>` spanning all columns (achieved using `column-span: all`) and a series of paragraphs laid out in multiple columns using `column-width: 200px`. We also have a `<figure>` containing an image and a caption.

By default, it is possible for you to get a break between the image and its caption, which is not what we want. To avoid this, we have set `break-inside: avoid` on the `<figure>`, which causes them to always stay together.

#### HTML

    <article>
      <h1>Main heading</h1>

      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla vitae fringilla mauris. Quisque commodo eget nisi sed pretium. Mauris luctus nec lacus in ultricies. Mauris vitae hendrerit arcu, ac scelerisque lacus. Aliquam lobortis in lacus sit amet posuere. Fusce iaculis urna id neque dapibus, eu lacinia lectus dictum.</p>

      <figure>
        <img src="https://media.prod.mdn.mozit.cloud/attachments/2020/07/29/17350/3b4892b7e820122ac6dd7678891d4507/firefox.png">
        <figcaption>The Firefox logo — fox wrapped around the world</figcaption>
      </figure>

      <p>Praesent condimentum dui dui, sit amet rutrum diam tincidunt eu. Cras suscipit porta leo sit amet rutrum. Sed vehicula ornare tincidunt. Curabitur a ipsum ac diam mattis volutpat ac ut elit. Nullam luctus justo non vestibulum gravida. Morbi metus libero, pharetra non porttitor a, molestie nec nisi.</p>

      <p>In finibus viverra enim vel suscipit. Quisque consequat velit eu orci malesuada, ut interdum tortor molestie. Proin sed pellentesque augue. Nam risus justo, faucibus non porta a, congue vel massa. Cras luctus lacus nisl, sed tincidunt velit pharetra ac. Duis suscipit faucibus dui sed ultricies.</p>
    </article>

#### CSS

    html {
      font-family: helvetica, arial, sans-serif;
    }

    body {
      width: 80%;
      margin: 0 auto;
    }

    h1 {
      font-size: 3rem;
      letter-spacing: 2px;
      column-span: all;
    }

    h1 + p {
      margin-top: 0;
    }

    p {
      line-height: 1.5;
      break-after: column;
    }

    figure {
      break-inside: avoid;
    }

    img {
      max-width: 70%;
      display: block;
      margin: 0 auto;
    }

    figcaption {
      font-style: italic;
      font-size: 0.8rem;
      width: 70%;
    }

    article {
      column-width: 200px;
      gap: 20px;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-break-3/#break-within">CSS Fragmentation Module Level 3<br />
<span class="small">The definition of 'break-inside' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-regions-1/#region-flow-break">CSS Regions Module Level 1<br />
<span class="small">The definition of 'break-inside' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Extends the property to handle region breaks.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-multicol-1/#break-before-break-after-break-inside">CSS Multi-column Layout Module<br />
<span class="small">The definition of 'break-inside' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`multicol_context`

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

`paged_context`

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

### Notes on compatibility

Prior to Firefox 65, the older property of [`page-break-inside`](page-break-inside) will work in Firefox to prevent breaks in columns, as well as pages. Add both properties for backwards compatibility.

For older WebKit-based browsers, the prefixed property `-webkit-column-break-inside` can be used to control column breaks.

## See also

- [Multiple-column Layout](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Multiple-column_Layout)
- [Breaking Boxes With CSS Fragmentation](https://www.smashingmagazine.com/2019/02/css-fragmentation/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/break-inside" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/break-inside</a>
