# text-decoration-thickness

The `text-decoration-thickness` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the stroke thickness of the decoration line that is used on text in an element, such as a line-through, underline, or overline.

## Syntax

    /* Single keyword */
    text-decoration-thickness: auto;
    text-decoration-thickness: from-font;

    /* length */
    text-decoration-thickness: 0.1em;
    text-decoration-thickness: 3px;

    /* percentage */
    text-decoration-thickness: 10%;

    /* Global values */
    text-decoration-thickness: inherit;
    text-decoration-thickness: initial;
    text-decoration-thickness: unset;

### Values

`auto`  
The browser chooses an appropriate width for the text decoration line.

`from-font`  
If the font file includes information about a preferred thickness, use that value. If the font file doesn't include this information, behave as if `auto` was set, with the browser choosing an appropriate thickness.

`<length>`  
Specifies the thickness of the text decoration line as a [`<length>`](length), overriding the font file suggestion or the browser default.

`<percentage>`  
Specifies the thickness of the text decoration line as a [`<percentage>`](percentage) of **1em** in the current font. A percentage inherits as a relative value, and so therefore scales with changes in the font. The browser must use a minimum of 1 device pixel. For a given application of this property, the thickness is constant across the whole box it is applied to, even if there are child elements with a different font size.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the font size of the element itself</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="even"><td>Animation type</td><td>by computed value type</td></tr></tbody></table>

## Formal syntax

    auto | from-font | <length> | <percentage>

## Examples

### Varying thickness

#### HTML

    <p class="thin">Here's some text with a 1px red underline.</p>
    <p class="thick">This one has a 5px red underline.</p>
    <p class="shorthand">This uses the equivalent shorthand.</p>

#### CSS

    .thin {
      text-decoration-line: underline;
      text-decoration-style: solid;
      text-decoration-color: red;
      text-decoration-thickness: 1px;
    }

    .thick {
      text-decoration-line: underline;
      text-decoration-style: solid;
      text-decoration-color: red;
      text-decoration-thickness: 5px;
    }

    .shorthand {
      text-decoration: underline solid red 5px;
    }

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-decor-4/#text-decoration-width-property">CSS Text Decoration Module Level 4<br />
<span class="small">The definition of 'text-decoration-width' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

**Note**: The property used to be called `text-decoration-width`, but was updated in 2019 to `text-decoration-thickness`.

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

`text-decoration-thickness`

89

87-89

The `text-decoration-thickness` property does not work unless either `text-underline-offset` is set to something other than `auto` or `text-decoration-color` is set to something other than `currentColor`. See [Chromium bug 1154537](https://crbug.com/1154537)

89

87-89

The `text-decoration-thickness` property does not work unless either `text-underline-offset` is set to something other than `auto` or `text-decoration-color` is set to something other than `currentColor`. See [Chromium bug 1154537](https://crbug.com/1154537)

70

69

No

75

73-75

The `text-decoration-thickness` property does not work unless either `text-underline-offset` is set to something other than `auto` or `text-decoration-color` is set to something other than `currentColor`. See [Chromium bug 1154537](https://crbug.com/1154537)

12.1

89

87-89

The `text-decoration-thickness` property does not work unless either `text-underline-offset` is set to something other than `auto` or `text-decoration-color` is set to something other than `currentColor`. See [Chromium bug 1154537](https://crbug.com/1154537)

89

87-89

The `text-decoration-thickness` property does not work unless either `text-underline-offset` is set to something other than `auto` or `text-decoration-color` is set to something other than `currentColor`. See [Chromium bug 1154537](https://crbug.com/1154537)

No

No

12.2

No

`percentage`

No

No

74

No

No

No

No

No

No

No

No

No

## See also

- [`text-decoration`](text-decoration)
- [`text-underline-offset`](text-underline-offset)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-thickness" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-decoration-thickness</a>
