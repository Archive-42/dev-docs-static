# font-stretch

The `font-stretch` CSS descriptor allows authors to specify a normal, condensed, or expanded face for the fonts specified in the [`@font-face`](../@font-face) rule.

For a particular font family, authors can download various font faces which correspond to the different styles of the same font family, and then use the `font-stretch `descriptor to explicitly specify the font face's stretch. The values for the CSS descriptor is same as that of its corresponding font property.

## Syntax

    /* Single values */
    font-stretch: ultra-condensed;
    font-stretch: extra-condensed;
    font-stretch: condensed;
    font-stretch: semi-condensed;
    font-stretch: normal;
    font-stretch: semi-expanded;
    font-stretch: expanded;
    font-stretch: extra-expanded;
    font-stretch: ultra-expanded;
    font-stretch: 50%;
    font-stretch: 100%;
    font-stretch: 200%;

    /* multiple values */
    font-stretch: 75% 125%;
    font-stretch: condensed ultra-condensed;;

The `font-weight` property is described using any one of the values listed below.

### Values

`normal`  
Specifies a normal font face.

`semi-condensed`, `condensed`, `extra-condensed`, `ultra-condensed`  
Specifies a more condensed font face than normal, with ultra-condensed as the most condensed.

`semi-expanded`, `expanded`, `extra-expanded`, `ultra-expanded`  
Specifies a more expanded font face than normal, with ultra-expanded as the most expanded.

`<percentage>`  
A [`<percentage>`](../percentage) value between 50% and 200% (inclusive). Negative values are not allowed for this property.

In earlier versions of the `font-stretch` specification, the property accepts only the nine keyword values. CSS Fonts Level 4 extends the syntax to accept a `<percentage>` value as well. This enables variable fonts to offer something more like a continuum of character widths. For TrueType or OpenType variable fonts, the "wdth" variation is used to implement varying widths.

If the font does not provide a face that exactly matches the given value, then values less than 100% map to a narrower face, and values greater than or equal to 100% map to a wider face.

### Keyword to numeric mapping

The table below shows the mapping between keyword values and numeric percentages:

<table><thead><tr class="header"><th>Keyword</th><th>Percentage</th></tr></thead><tbody><tr class="odd"><td><code>ultra-condensed</code></td><td>50%</td></tr><tr class="even"><td><code>extra-condensed</code></td><td>62.5%</td></tr><tr class="odd"><td><code>condensed</code></td><td>75%</td></tr><tr class="even"><td><code>semi-condensed</code></td><td>87.5%</td></tr><tr class="odd"><td><code>normal</code></td><td>100%</td></tr><tr class="even"><td><code>semi-expanded</code></td><td>112.5%</td></tr><tr class="odd"><td><code>expanded</code></td><td>125%</td></tr><tr class="even"><td><code>extra-expanded</code></td><td>150%</td></tr><tr class="odd"><td><code>ultra-expanded</code></td><td>200%</td></tr></tbody></table>

### Variable fonts

Most fonts have a particular width which corresponds to one of the keyterm values. However some fonts, called variable fonts, can support a range of stretching with more or less fine granularity, and this can give the designer a much closer degree of control over the chosen weight. For this, percentage ranges are useful.

For TrueType or OpenType variable fonts, the "wdth" variation is used to implement varying glyph widths.

## Accessibility concerns

People with dyslexia and other cognitive conditions may have difficulty reading fonts that are too condensed, especially if the font has a [low contrast color ratio](../color#accessibility_concerns).

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.8 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-visual-presentation.html)

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@font-face"><code>@font-face</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified</td></tr></tbody></table>

## Formal syntax

    <font-stretch-absolute>{1,2}where
    <font-stretch-absolute> = normal | ultra-condensed | extra-condensed | condensed | semi-condensed | semi-expanded | expanded | extra-expanded | ultra-expanded | <percentage>

## Examples

### Setting a percentage range for font-stretch

The following find a local Open Sans font or import it, and allow using the font for normal, semi-condensed and semi-expanded states.

    @font-face {
      font-family: "Open Sans";
      src: local("Open Sans") format("woff2"),
           url("/fonts/OpenSans-Regular-webfont.woff") format("woff");
      font-stretch: 87.5% 112.5%;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#font-prop-desc">CSS Fonts Module Level 4<br />
<span class="small">The definition of 'font-stretch' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-fonts-3/#font-prop-desc">CSS Fonts Module Level 3<br />
<span class="small">The definition of 'font-stretch' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`font-stretch`

62

17

62

No

49

10.1

62

62

62

41

10.3

6.0

## See also

- [`font-display`](font-display)
- [`font-family`](font-family)
- [`font-weight`](font-weight)
- [`font-style`](font-style)
- [`font-variant`](font-variant)
- [`font-feature-settings`](../font-feature-settings)
- [`font-variation-settings`](font-variation-settings)
- [`src`](src)
- [`unicode-range descriptor`](unicode-range)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-stretch" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@font-face/font-stretch</a>
