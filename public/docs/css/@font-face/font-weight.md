# font-weight

The `font-weight` CSS descriptor allows authors to specify font weights for the fonts specified in the [`@font-face`](../@font-face) rule. The [`font-weight`](../font-weight) property can separately be used to set how thick or thin characters in text should be displayed.

For a particular font family, authors can download various font faces which correspond to the different styles of the same font family, and then use the `font-weight `descriptor to explicitly specify the font face's weights. The values for the CSS descriptor is same as that of its corresponding font property.

There are generally limited weights available for a particular font family. When a specified weight doesn't exist, a nearby weight is used. Fonts lacking bold are often synthesized by the user agent. To prevent this, use [`font-synthesis`](../font-synthesis) property.

## Syntax

    /* Single values */
    font-weight: normal;
    font-weight: bold;
    font-weight: 400;

    /* Multiple Values */
    font-weight: normal bold;
    font-weight: 300 500;

The `font-weight` property is described using any one of the values listed below.

### Values

`normal`  
Normal font weight. Same as `400`.

`bold`  
Bold font weight. Same as `700`.

`<number>`  
A [`<number>`](../number) value between 1 and 1000, inclusive. Higher numbers represent weights that are bolder than (or as bold as) lower numbers. Certain commonly used values correspond to common weight names, as described in the [Common weight name mapping](#common_weight_name_mapping) section below.

In earlier versions of the `font-weight` specification, the property accepts only keyword values and the numeric values 100, 200, 300, 400, 500, 600, 700, 800, and 900; non-variable fonts can only really make use of these set values, although fine-grained values (e.g. 451) will be translated to one of these values for non-variable fonts.

CSS Fonts Level 4 extends the syntax to accept any number between 1 and 1000, inclusive, and introduces [Variable fonts](#variable_fonts), which can make use of this much finer-grained range of font weights.

### Common weight name mapping

The numerical values `100` to `900` roughly correspond to the following common weight names:

<table><thead><tr class="header"><th>Value</th><th>Common weight name</th></tr></thead><tbody><tr class="odd"><td>100</td><td>Thin (Hairline)</td></tr><tr class="even"><td>200</td><td>Extra Light (Ultra Light)</td></tr><tr class="odd"><td>300</td><td>Light</td></tr><tr class="even"><td>400</td><td>Normal</td></tr><tr class="odd"><td>500</td><td>Medium</td></tr><tr class="even"><td>600</td><td>Semi Bold (Demi Bold)</td></tr><tr class="odd"><td>700</td><td>Bold</td></tr><tr class="even"><td>800</td><td>Extra Bold (Ultra Bold)</td></tr><tr class="odd"><td>900</td><td>Black (Heavy)</td></tr></tbody></table>

### Variable fonts

Most fonts have a particular weight which corresponds to one of the numbers in [Common weight name mapping](#common_weight_name_mapping). However some fonts, called variable fonts, can support a range of weights with more or less fine granularity, and this can give the designer a much closer degree of control over the chosen weight.

For TrueType or OpenType variable fonts, the "wght" variation is used to implement varying weights.

## Accessibility concerns

People experiencing low vision conditions may have difficulty reading text set with a `font-weight` value of `100` (Thin/Hairline) or `200` (Extra Light), especially if the font has a [low contrast color ratio](../color#accessibility_concerns).

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.8 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-visual-presentation.html)

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@font-face"><code>@font-face</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified</td></tr></tbody></table>

## Formal syntax

    <font-weight-absolute>{1,2}where
    <font-weight-absolute> = normal | bold | [1,1000]>

## Examples

### Setting normal font weight in a @font-face rule

The following finds a local Open Sans font or imports it, and allows using the font for normal font weights.

    @font-face {
      font-family: "Open Sans";
      src: local("Open Sans") format("woff2"),
           url("/fonts/OpenSans-Regular-webfont.woff") format("woff");
      font-weight: 400;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#font-prop-desc">CSS Fonts Module Level 4<br />
<span class="small">The definition of 'font-weight' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-fonts-3/#font-prop-desc">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font-weight' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`font-weight`

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
- [`font-stretch`](font-stretch)
- [`font-style`](font-style)
- [`font-variant`](font-variant)
- [`font-feature-settings`](../font-feature-settings)
- [`font-variation-settings`](font-variation-settings)
- [`src`](src)
- [`unicode-range descriptor`](unicode-range)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-weight" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-weight</a>
