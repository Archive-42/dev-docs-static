# font-family

The `font-family` CSS descriptor allows authors to specify the font family for the font specified in an [`@font-face`](../@font-face) rule.

## Syntax

    /* <string> values */
    font-family: "font family";
    font-family: 'another font family';

    /* <custom-ident> value */
    font-family: examplefont;

### Values

`<family-name>`  
Specifies the name of the font family.

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@font-face"><code>@font-face</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>n/a (required)</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified</td></tr></tbody></table>

## Formal syntax

    <family-name>where
    <family-name> = <string> | <custom-ident>+

## Examples

### Setting the font family name

    @font-face {
      font-family: examplefont;
      src: url('examplefont.ttf');
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-3/#font-family-desc">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font-family' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`font-family`

4

12

3.5

6

10

3.1

2.2

18

4

10.1

3.1

1.0

## See also

- [`font-display`](font-display)
- [`font-stretch`](font-stretch)
- [`font-style`](font-style)
- [`font-weight`](font-weight)
- [`font-variant`](font-variant)
- [`font-feature-settings`](../font-feature-settings)
- [`font-variation-settings`](font-variation-settings)
- [`src`](src)
- [`unicode-range`](unicode-range)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-family" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-family</a>
