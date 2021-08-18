# text-emphasis-style

The `text-emphasis-style` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the appearance of emphasis marks. It can also be set, and reset, using the [`text-emphasis`](text-emphasis) shorthand.

    /* Initial value */
    text-emphasis-style: none; /* No emphasis marks */

    /* <string> values */
    text-emphasis-style: 'x';
    text-emphasis-style: '点';
    text-emphasis-style: '\25B2';
    text-emphasis-style: '*';
    text-emphasis-style: 'foo'; /* Should NOT be used. It may be computed to or rendered as 'f' only */

    /* Keyword values */
    text-emphasis-style: filled;
    text-emphasis-style: open;
    text-emphasis-style: dot;
    text-emphasis-style: circle;
    text-emphasis-style: double-circle;
    text-emphasis-style: triangle;
    text-emphasis-style: filled sesame;
    text-emphasis-style: open sesame;

    /* Global values */
    text-emphasis-style: inherit;
    text-emphasis-style: initial;
    text-emphasis-style: unset;

## Syntax

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
Display large circles as marks. The filled circle is `'●'` (`U+25CF`), and the open circle is `'○'` (`U+25CB`).

`double-circle`  
Display double circles as marks. The filled double-circle is `'◉'` (`U+25C9`), and the open double-circle is `'◎'` (`U+25CE`).

`triangle`  
Display triangles as marks. The filled triangle is `'▲'` (`U+25B2`), and the open triangle is `'△'` (`U+25B3`).

`sesame`  
Display sesames as marks. The filled sesame is `'﹅'` (`U+FE45`), and the open sesame is `'﹆'` (`U+FE46`).

`<string>`  
Display the given string as marks. Authors should not specify more than one _character_ in `<string>`. The UA may truncate or ignore strings consisting of more than one grapheme cluster.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | [ [ filled | open ] || [ dot | circle | double-circle | triangle | sesame ] ] | <string>

## Examples

### Basic example

    h2 {
      text-emphasis-style: sesame;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-text-decor-3/#text-emphasis-style-property">CSS Text Decoration Module Level 3<br />
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

`text-emphasis-style`

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

- The related properties [`text-emphasis-color`](text-emphasis-color), [`text-emphasis`](text-emphasis).
- The [`text-emphasis-position`](text-emphasis-position) property allowing to define the position of the emphasis marks.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-emphasis-style</a>
