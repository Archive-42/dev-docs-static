# fit-content

The `fit-content` behaves as `fit-content(stretch)`. In practice this means that the box will use the available space, but never more than [`max-content`](max-content).

When used as laid out box size for [`width`](width), [`height`](height), [`min-width`](min-width), [`min-height`](min-height), [`max-width`](max-width) and [`max-height`](max-height) the maximum and minimum sizes refer to the content size.

The CSS Sizing specification also defines the [`fit-content()`](<fit-content()>) function. This page details the keyword.

## Syntax

    width: fit-content
    block-size: fit-content

## Examples

### Using fit-content for box sizing

#### HTML

    <div class="container">
      <div class="item">Item</div>
      <div class="item">Item with more text in it.</div>
      <div class="item">Item with more text in it, hopefully we have added enough text so the text will start to wrap.</div>
    </div>

#### CSS

    .container {
      border: 2px solid #ccc;
      padding: 10px;
      width: 20em;
    }

    .item {
      width: -moz-fit-content;
      width: fit-content;
      background-color: #8ca0ff;
      padding: 5px;
      margin-bottom: 1em;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-sizing-4/#valdef-width-fit-content">CSS Box Sizing Module Level 4<br />
<span class="small">The definition of 'fit-content' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Defines the value as laid out box size for <a href="width"><code>width</code></a>, <a href="height"><code>height</code></a>, <a href="min-width"><code>min-width</code></a>, <a href="min-height"><code>min-height</code></a>, <a href="max-width"><code>max-width</code></a> and <a href="max-height"><code>max-height</code></a>.</td></tr></tbody></table>

## Browser compatibility

### Supported for width (and other sizing properties)

BCD tables only load in the browser

## See also

- Related sizing keywords: [`min-content`](min-content), [`max-content`](max-content)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/fit-content" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/fit-content</a>
