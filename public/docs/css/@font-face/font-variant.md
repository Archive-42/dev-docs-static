# font-variant

The `font-variant` CSS [shorthand property](../shorthand_properties) allows you to set all the font variants for the fonts specified in the [`@font-face`](../@font-face) rule.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`font-variant-alternates`](../font-variant-alternates)
- [`font-variant-caps`](../font-variant-caps)
- [`font-variant-east-asian`](../font-variant-east-asian)
- [`font-variant-ligatures`](../font-variant-ligatures)
- [`font-variant-numeric`](../font-variant-numeric)

## Syntax

    font-variant: small-caps;
    font-variant: common-ligatures small-caps;

    /* Global values */
    font-variant: inherit;
    font-variant: initial;
    font-variant: unset;

### Values

`normal`  
Specifies a normal font face; each of the longhand properties has an initial value of normal. Longhand properties of `font-variant` are: [`font-variant-caps`](../font-variant-caps), [`font-variant-numeric`](../font-variant-numeric), [`font-variant-alternates`](../font-variant-alternates), [`font-variant-ligatures`](../font-variant-ligatures), and [`font-variant-east-asian`](../font-variant-east-asian).

`none`  
Sets the value of the [`font-variant-ligatures`](../font-variant-ligatures) to `none` and the values of the other longhand property as `normal`, their initial value.

`<common-lig-values>`, `<discretionary-lig-values>`, `<historical-lig-values>`, `<contextual-alt-values>`  
Specifies the keywords related to the [`font-variant-ligatures`](../font-variant-ligatures) longhand property. The possible values are: `common-ligatures`, `no-common-ligatures`, `discretionary-ligatures`, `no-discretionary-ligatures`, `historical-ligatures`, `no-historical-ligatures`, `contextual`, and `no-contextual`.

`stylistic()`, `historical-forms`, `styleset()`, `character-variant()`, `swash()`, `ornaments()`, `annotation()`  
Specifies the keywords and functions related to the [`font-variant-alternates`](../font-variant-alternates) longhand property.

`small-caps`, `all-small-caps`, `petite-caps`, `all-petite-caps`, `unicase`, `titling-caps`  
Specifies the keywords and functions related to the [`font-variant-caps`](../font-variant-caps) longhand property.

`<numeric-figure-values>`, `<numeric-spacing-values>`, `<numeric-fraction-values>`, `ordinal`, `slashed-zero`  
Specifies the keywords related to the [`font-variant-numeric`](../font-variant-numeric) longhand property. The possible values are: `lining-nums`, `oldstyle-nums`, `proportional-nums`, `tabular-nums`, `diagonal-fractions`, `stacked-fractions`, `ordinal`, and `slashed-zero`.

`<east-asian-variant-values>`, `<east-asian-width-values>`, `ruby`  
Specifies the keywords related to the [`font-variant-east-asian`](../font-variant-east-asian) longhand property. The possible values are: `jis78`, `jis83`, `jis90`, `jis04`, `simplified`, `traditional`, `full-width`, `proportional-width`, `ruby`.

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@font-face"><code>@font-face</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified</td></tr></tbody></table>

## Formal syntax

    normal | none | [ <common-lig-values> || <discretionary-lig-values> || <historical-lig-values> || <contextual-alt-values> || stylistic(<feature-value-name>) || historical-forms || styleset(<feature-value-name>#) || character-variant(<feature-value-name>#) || swash(<feature-value-name>) || ornaments(<feature-value-name>) || annotation(<feature-value-name>) || [ small-caps | all-small-caps | petite-caps | all-petite-caps | unicase | titling-caps ] || <numeric-figure-values> || <numeric-spacing-values> || <numeric-fraction-values> || ordinal || slashed-zero || <east-asian-variant-values> || <east-asian-width-values> || ruby ]where
    <common-lig-values> = [ common-ligatures | no-common-ligatures ]
    <discretionary-lig-values> = [ discretionary-ligatures | no-discretionary-ligatures ]
    <historical-lig-values> = [ historical-ligatures | no-historical-ligatures ]
    <contextual-alt-values> = [ contextual | no-contextual ]
    <feature-value-name> = <custom-ident>
    <numeric-figure-values> = [ lining-nums | oldstyle-nums ]
    <numeric-spacing-values> = [ proportional-nums | tabular-nums ]
    <numeric-fraction-values> = [ diagonal-fractions | stacked-fractions ]
    <east-asian-variant-values> = [ jis78 | jis83 | jis90 | jis04 | simplified | traditional ]
    <east-asian-width-values> = [ full-width | proportional-width ]

## Examples

### Setting the small-caps font variant

The following finds a local Open Sans font or imports it, and allows using the font for small-caps.

    @font-face {
      font-family: "Open Sans";
      src: local("Open Sans") format("woff2"),
           url("/fonts/OpenSans-Regular-webfont.woff") format("woff");
      font-variant: small-caps;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#font-prop-desc">CSS Fonts Module Level 4<br />
<span class="small">The definition of 'font-variant' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-fonts-3/#font-prop-desc">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font-variant' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`font-variant`

4

12

3.5

4

10

3.1

≤37

18

4

10.1

2

1.0

## See also

- [`font-display`](font-display)
- [`font-family`](font-family)
- [`font-weight`](font-weight)
- [`font-style`](font-style)
- [`font-stretch`](font-variant)
- [`font-feature-settings`](../font-feature-settings)
- [`font-variation-settings`](font-variation-settings)
- [`src`](src)
- [`unicode-range descriptor`](unicode-range)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-variant" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-variant</a>
