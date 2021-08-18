# text-orientation

The `text-orientation` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the orientation of the text characters in a line. It only affects text in vertical mode (when [`writing-mode`](writing-mode) is not `horizontal-tb`). It is useful for controlling the display of languages that use vertical script, and also for making vertical table headers.

## Syntax

    /* Keyword values */
    text-orientation: mixed;
    text-orientation: upright;
    text-orientation: sideways-right;
    text-orientation: sideways;
    text-orientation: use-glyph-orientation;

    /* Global values */
    text-orientation: inherit;
    text-orientation: initial;
    text-orientation: unset;

The `text-orientation` property is specified as a single keyword from the list below.

### Values

`mixed`  
Rotates the characters of horizontal scripts 90° clockwise. Lays out the characters of vertical scripts naturally. Default value.

`upright`  
Lays out the characters of horizontal scripts naturally (upright), as well as the glyphs for vertical scripts. Note that this keyword causes all characters to be considered as left-to-right: the used value of [`direction`](direction) is forced to be `ltr`.

`sideways`  
Causes characters to be laid out as they would be horizontally, but with the whole line rotated 90° clockwise.

`sideways-right`  
An alias to `sideways` that is kept for compatibility purposes.

`use-glyph-orientation`  
On SVG elements, this keyword leads to use the value of the deprecated SVG properties `glyph-orientation-vertical` and `glyph-orientation-horizontal`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>mixed</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, except table row groups, rows, column groups, and columns</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    mixed | upright | sideways

## Examples

### HTML

    <p>Lorem ipsum dolet semper quisquam.</p>

### CSS

    p {
      writing-mode: vertical-rl;
      text-orientation: upright;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-writing-modes-3/#text-orientation">CSS Writing Modes Module Level 3<br />
<span class="small">The definition of 'text-orientation' in that specification.</span></a></td><td><span class="spec-pr">Proposed Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`text-orientation`

48

11

79

79

41

No

15

14

5.1

48

≤37

48

18

41

14

14

5

5.0

1.0

`sideways`

No

No

44

`sideways-right` has become an alias of `sideways`.

No

No

No

No

No

44

`sideways-right` has become an alias of `sideways`.

No

No

No

## See also

- The other vertical-script related CSS properties: [`writing-mode`](writing-mode), [`text-combine-upright`](text-combine-upright), and [`unicode-bidi`](unicode-bidi).
- [CSS Logical properties](css_logical_properties)
- [Styling vertical text (Chinese, Japanese, Korean and Mongolian)](https://www.w3.org/International/articles/vertical-text/)
- Extensive browsers support test results: <https://w3c.github.io/i18n-tests/results/horizontal-in-vertical.html#text_orientation>

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-orientation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-orientation</a>
