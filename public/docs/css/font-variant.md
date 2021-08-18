# font-variant

The `font-variant` CSS [shorthand property](shorthand_properties) allows you to set all the font variants for a font.

You can also set the CSS Level 2 (Revision 1) values of `font-variant`, (that is, `normal` or `small-caps`), by using the [`font`](font) shorthand.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`font-variant-alternates`](font-variant-alternates)
- [`font-variant-caps`](font-variant-caps)
- [`font-variant-east-asian`](font-variant-east-asian)
- [`font-variant-ligatures`](font-variant-ligatures)
- [`font-variant-numeric`](font-variant-numeric)

## Syntax

    font-variant: small-caps;
    font-variant: common-ligatures small-caps;

    /* Global values */
    font-variant: inherit;
    font-variant: initial;
    font-variant: unset;

### Values

`normal`  
Specifies a normal font face; each of the longhand properties has an initial value of normal. Longhand properties of `font-variant` are: [`font-variant-caps`](font-variant-caps), [`font-variant-numeric`](font-variant-numeric), [`font-variant-alternates`](font-variant-alternates), [`font-variant-ligatures`](font-variant-ligatures), and [`font-variant-east-asian`](font-variant-east-asian).

`none`  
Sets the value of the [`font-variant-ligatures`](font-variant-ligatures) to `none` and the values of the other longhand property as `normal`, their initial value.

`<common-lig-values>`, `<discretionary-lig-values>`, `<historical-lig-values>`, `<contextual-alt-values>`  
Specifies the keywords related to the [`font-variant-ligatures`](font-variant-ligatures) longhand property. The possible values are: `common-ligatures`, `no-common-ligatures`, `discretionary-ligatures`, `no-discretionary-ligatures`, `historical-ligatures`, `no-historical-ligatures`, `contextual`, and `no-contextual`.

`stylistic()`, `historical-forms`, `styleset()`, `character-variant()`, `swash()`, `ornaments()`, `annotation()`  
Specifies the keywords and functions related to the [`font-variant-alternates`](font-variant-alternates) longhand property.

`small-caps`, `all-small-caps`, `petite-caps`, `all-petite-caps`, `unicase`, `titling-caps`  
Specifies the keywords and functions related to the [`font-variant-caps`](font-variant-caps) longhand property.

`<numeric-figure-values>`, `<numeric-spacing-values>`, `<numeric-fraction-values>`, `ordinal`, `slashed-zero`  
Specifies the keywords related to the [`font-variant-numeric`](font-variant-numeric) longhand property. The possible values are: `lining-nums`, `oldstyle-nums`, `proportional-nums`, `tabular-nums`, `diagonal-fractions`, `stacked-fractions`, `ordinal`, and `slashed-zero`.

`<east-asian-variant-values>`, `<east-asian-width-values>`, `ruby`  
Specifies the keywords related to the [`font-variant-east-asian`](font-variant-east-asian) longhand property. The possible values are: `jis78`, `jis83`, `jis90`, `jis04`, `simplified`, `traditional`, `full-width`, `proportional-width`, `ruby`.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | none | [ <common-lig-values> || <discretionary-lig-values> || <historical-lig-values> || <contextual-alt-values> || stylistic( <feature-value-name> ) || historical-forms || styleset( <feature-value-name># ) || character-variant( <feature-value-name># ) || swash( <feature-value-name> ) || ornaments( <feature-value-name> ) || annotation( <feature-value-name> ) || [ small-caps | all-small-caps | petite-caps | all-petite-caps | unicase | titling-caps ] || <numeric-figure-values> || <numeric-spacing-values> || <numeric-fraction-values> || ordinal || slashed-zero || <east-asian-variant-values> || <east-asian-width-values> || ruby ]where
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

#### HTML

    <p class="normal">Firefox rocks!</p>
    <p class="small">Firefox rocks!</p>

#### CSS

    p.normal {
      font-variant: normal;
    }
    p.small {
      font-variant: small-caps;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-3/#propdef-font-variant">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font-variant' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Made it a shorthand of the new <code>font-variant-*</code> properties.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/fonts.html#propdef-font-variant">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'font-variant' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#font-variant">CSS Level 1<br />
<span class="small">The definition of 'font-variant' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

1

12

1

4

3.5

1

1

18

4

11

1

1.0

`css_fonts_shorthand`

52

79

34

No

39

9.1

52

52

34

41

9.3

6.0

`greek_accented_characters`

No

Some operating systems may correctly omit accents in all-uppercase Greek text.

No

Some operating systems may correctly omit accents in all-uppercase Greek text.

No

Some operating systems may correctly omit accents in all-uppercase Greek text.

No

No

Some operating systems may correctly omit accents in all-uppercase Greek text.

No

No

Some operating systems may correctly omit accents in all-uppercase Greek.

No

Some operating systems may correctly omit accents in all-uppercase Greek text.

No

Some operating systems may correctly omit accents in all-uppercase Greek text.

No

Some operating systems may correctly omit accents in all-uppercase Greek text.

No

No

Some operating systems may correctly omit accents in all-uppercase Greek text.

`turkic_is`

31

12

14

4

18

8

≤37

31

14

18

8

2.0

`uppercase_eszett`

No

Some operating systems may capitalize `ß` as `SS`.

No

Some operating systems may capitalize `ß` as `SS`.

No

Some operating systems may capitalize `ß` as `SS`.

No

No

Some operating systems may capitalize `ß` as `SS`.

No

No

Some operating systems may capitalize `ß` as `SS`.

No

Some operating systems may capitalize `ß` as `SS`.

No

Some operating systems may capitalize `ß` as `SS`.

No

Some operating systems may capitalize `ß` as `SS`.

No

No

Some operating systems may capitalize `ß` as `SS`.

## See also

- [`text-transform`](text-transform)
- [`text-combine-upright`](text-combine-upright)
- [`text-orientation`](text-orientation)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/font-variant</a>
