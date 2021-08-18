# text-emphasis

The `text-emphasis` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property applies emphasis marks to text (except spaces and control characters). It is a [shorthand](shorthand_properties) for [`text-emphasis-style`](text-emphasis-style) and [`text-emphasis-color`](text-emphasis-color).

The `text-emphasis` property is quite different from [`text-decoration`](text-decoration). The `text-decoration` property does not inherit, and the decoration specified is applied across the whole element. However, text-emphasis does inherit, which means it is possible to change emphasis marks for descendants.

The size of the emphasis symbol, like ruby symbols, is about 50% of the size of the font, and `text-emphasis` may affect line height when the current leading is not enough for the marks.

`text-emphasis` doesn't reset the value of [`text-emphasis-position`](text-emphasis-position). This is because if the style and the color of emphasis marks may vary in a text, it is extremely unlikely that their position will. In the very rare cases when this is needed, the property [`text-emphasis-position`](text-emphasis-position).

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`text-emphasis-color`](text-emphasis-color)
- [`text-emphasis-style`](text-emphasis-style)

## Syntax

    /* Initial value */
    text-emphasis: none; /* No emphasis marks */

    /* <string> value */
    text-emphasis: 'x';
    text-emphasis: '点';
    text-emphasis: '\25B2';
    text-emphasis: '*' #555;
    text-emphasis: 'foo'; /* Should NOT use. It may be computed to or rendered as 'f' only */

    /* Keywords value */
    text-emphasis: filled;
    text-emphasis: open;
    text-emphasis: filled sesame;
    text-emphasis: open sesame;

    /* Keywords value combined with a color */
    text-emphasis: filled sesame #555;

    /* Global values */
    text-emphasis: inherit;
    text-emphasis: initial;
    text-emphasis: unset;

### Values

`none`  
No emphasis marks.

`filled`  
The shape is filled with solid color. If neither `filled` nor `open` is present, this is the default.

`open`  
The shape is hollow.

`dot`  
Display small circles as marks. The filled dot is `'•'` (`U+2022`), and the open dot is `'◦'` (`U+25E6`).

`circle`  
Display large circles as marks. The filled circle is `'●'` (`U+25CF`), and the open circle is `'○'` (`U+25CB`). This is the default shape in horizontal writing modes when no other shape is given.

`double-circle`  
Display double circles as marks. The filled double-circle is `'◉'` (`U+25C9`), and the open double-circle is `'◎'` (`U+25CE`).

`triangle`  
Display triangles as marks. The filled triangle is `'▲'` (`U+25B2`), and the open triangle is `'△'` (`U+25B3`).

`sesame`  
Display sesames as marks. The filled sesame is `'﹅'` (`U+FE45`), and the open sesame is `'﹆'` (`U+FE46`). This is the default shape in vertical writing modes when no other shape is given.

`<string>`  
Display the given string as marks. Authors should not specify more than one _character_ in `<string>`. The UA may truncate or ignore strings consisting of more than one grapheme cluster.

`<color>`  
Defines the color of the mark. If no color is present, it defaults to `currentcolor`.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="text-emphasis-style"><code>text-emphasis-style</code></a>: <code>none</code></li><li><a href="text-emphasis-color"><code>text-emphasis-color</code></a>: <code>currentcolor</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="text-emphasis-style"><code>text-emphasis-style</code></a>: as specified</li><li><a href="text-emphasis-color"><code>text-emphasis-color</code></a>: computed color</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="text-emphasis-color"><code>text-emphasis-color</code></a>: a <a href="color_value#interpolation">color</a></li><li><a href="text-emphasis-style"><code>text-emphasis-style</code></a>: discrete</li></ul></td></tr></tbody></table>

## Formal syntax

    <'text-emphasis-style'> || <'text-emphasis-color'>

## Examples

### A heading with emphasis shape and color

This example draws a heading with triangles used to emphasize each character.

#### CSS

    h2 {
      text-emphasis: triangle #D55;
    }

#### HTML

    <h2>This is important!</h2>

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-decor-3/#text-emphasis-property">CSS Text Decoration Module Level 3<br />
<span class="small">The definition of 'text-emphasis' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`text-emphasis`

25

79

46

No

15

6.1

6.1

4.4

25

46

14

7

7

1.5

## See also

- The longhand properties [`text-emphasis-style`](text-emphasis-style), [`text-emphasis-color`](text-emphasis-color).
- The [`text-emphasis-position`](text-emphasis-position) property allowing to define the position of the emphasis marks.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis</a>
