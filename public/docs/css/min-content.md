# min-content

The `min-content` sizing keyword represents the intrinsic minimum width of the content. For text content this means that the content will take all soft-wrapping opportunities, becoming as small as the longest word.

## Syntax

    /* Used as a length */
    width: min-content;
    inline-size: min-content;
    height: min-content;
    block-size: min-content;

    /* used in grid tracks */
    grid-template-columns: 200px 1fr min-content;

## Examples

### Using min-content for box sizing

#### HTML

    <div class="item">Item</div>
    <div class="item">Item with more text in it.</div>

#### CSS

    .item {
      width: min-content;
      background-color: #8ca0ff;
      padding: 5px;
      margin-bottom: 1em;
    }

#### Result

### Sizing grid columns with min-content

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
      grid-template-columns: min-content min-content 1fr;
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-sizing-3/#valdef-width-min-content">CSS Box Sizing Module Level 3<br />
<span class="small">The definition of 'min-content' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Defines the keyword as laid out box size for <a href="width"><code>width</code></a>, <a href="height"><code>height</code></a>, <a href="min-width"><code>min-width</code></a>, <a href="min-height"><code>min-height</code></a>, <a href="max-width"><code>max-width</code></a> and <a href="max-height"><code>max-height</code></a>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-grid/#valdef-grid-template-columns-min-content">CSS Grid Layout<br />
<span class="small">The definition of 'min-content' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines the keyword when used as a track size.</td></tr></tbody></table>

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

`min-content`

46

1-48

79

66

3

No

33

15-35

11

2

46

1-48

46

18-48

66

4

33

14-35

11

1

5.0

1.0-5.0

### Supported for width (and other sizing properties)

BCD tables only load in the browser

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/min-content" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/min-content</a>
