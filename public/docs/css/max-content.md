# max-content

The `max-content` sizing keyword represents the intrinsic maximum width of the content. For text content this means that the content will not wrap at all even if it causes overflows.

## Syntax

    /* Used as a length */
    width: max-content;
    inline-size: max-content;
    height: max-content;
    block-size: max-content;

    /* used in grid tracks */
    grid-template-columns: 200px 1fr max-content;

## Examples

### Using max-content for box sizing

#### HTML

    <div id="container">
      <div class="item">Item</div>
      <div class="item">Item with more text in it which will overflow the fixed width box.</div>
    </div>

#### CSS

    #container {
      background-color: #8cffa0;
      padding: 10px;
      width: 200px;
    }

    .item {
      width: max-content;
      background-color: #8ca0ff;
      padding: 5px;
      margin-bottom: 1em;
    }

#### Result

### Sizing grid columns with max-content

#### HTML

    <div id="container">
      <div>Item</div>
      <div>
        Item with more text in it.
      </div>
      <div>Flexible item</div>
    </div>

#### CSS

    #container {
      display: grid;
      grid-template-columns: max-content max-content 1fr;
      grid-gap: 5px;
      box-sizing: border-box;
      height: 200px;
      width: 100%;
      background-color: #8cffa0;
      padding: 10px;
    }

    #container > div {
      background-color: #8ca0ff;
      padding: 5px;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-sizing-3/#valdef-width-max-content">CSS Box Sizing Module Level 3<br />
<span class="small">The definition of 'max-content' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Defines the keyword as laid out box size for <a href="width"><code>width</code></a>, <a href="height"><code>height</code></a>, <a href="min-width"><code>min-width</code></a>, <a href="min-height"><code>min-height</code></a>, <a href="max-width"><code>max-width</code></a> and <a href="max-height"><code>max-height</code></a>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-grid/#valdef-grid-template-columns-max-content">CSS Grid Layout<br />
<span class="small">The definition of 'max-content' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines the keyword when used as a track size.</td></tr></tbody></table>

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

`max-content`

46

22

79

79

66

3

No

44

11

2

46

46

66

4

43

11

1

5.0

### Supported for width (and other sizing properties)

BCD tables only load in the browser

## See also

- Related sizing keywords: [`min-content`](min-content), [`fit-content`](fit-content)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/max-content" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/max-content</a>
