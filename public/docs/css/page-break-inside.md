# page-break-inside

This property has been replaced by the [`break-inside`](break-inside) property.

The `page-break-inside` CSS property adjusts page breaks _inside_ the current element.

    /* Keyword values */
    page-break-inside: auto;
    page-break-inside: avoid;

    /* Global values */
    page-break-inside: inherit;
    page-break-inside: initial;
    page-break-inside: unset;

## Syntax

### Values

`auto`  
Initial value. Automatic page breaks (neither forced nor forbidden).

`avoid`  
Avoid page breaks inside the element.

## Page break aliases

The `page-break-inside` property is now a legacy property, replaced by [`break-inside`](break-inside).

For compatibility reasons, `page-break-inside` should be treated by browsers as an alias of `break-inside`. This ensures that sites using `page-break-inside` continue to work as designed. A subset of values should be aliased as follows:

<table><thead><tr class="header"><th>page-break-inside</th><th>break-inside</th></tr></thead><tbody><tr class="odd"><td><code>auto</code></td><td><code>auto</code></td></tr><tr class="even"><td><code>avoid</code></td><td><code>avoid</code></td></tr></tbody></table>

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>block-level elements in the normal flow of the root element. User agents may also apply it to other elements like <code>table-row</code> elements.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | avoid

## Examples

### Avoiding page breaks inside elements

#### HTML

    <div class="page">
      <p>This is the first paragraph.</p>
      <section class="list">
        <span>A list</span>
        <ol>
          <li>one</li>
    <!--       <li>two</li> -->
        </ol>
      </section>
      <ul>
        <li>one</li>
    <!--     <li>two</li> -->
      </ul>
      <p>This is the second paragraph.</p>
      <p>This is the third paragraph, it contains more text.</p>
      <p>This is the fourth paragraph. It has a little bit more text than the third one.</p>
    </div>

#### CSS

    .page {
      background-color: #8cffa0;
      height: 90px;
      width: 200px;
      columns: 1;
      column-width: 100px;
    }

    .list, ol, ul, p {
      break-inside: avoid;
    }

    p {
      background-color: #8ca0ff;
    }

    ol, ul, .list {
      margin: 0.5em 0;
      display: block;
      background-color: orange;
    }

    p:first-child {
      margin-top: 0;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-page-3/#page-break-inside">CSS Paged Media Module Level 3<br />
<span class="small">The definition of 'page-break-inside' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Allows this property on more elements.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/page.html#propdef-page-break-inside">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'page-break-inside' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`page-break-inside`

1

12

19

Until Firefox 25, ` page-break-inside``: avoid ` did not work with the height of a block.

8

7

1.3

37

18

19

Until Firefox 25, ` page-break-inside``: avoid ` did not work with the height of a block.

14

1

1.0

## See also

- [`break-before`](break-before), [`break-after`](break-after), [`break-inside`](break-inside)
- [`page-break-after`](page-break-after), [`page-break-before`](page-break-before)
- [`orphans`](orphans), [`widows`](widows)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/page-break-inside" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/page-break-inside</a>
