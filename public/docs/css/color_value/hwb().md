# hwb()

The `hwb()` functional notation expresses a given color according to its hue, whitness, and blackness. An optional alpha component represents the color's transparency.

## Syntax

    hwb(194 0% 0%) /* #00c3ff */
    hwb(194 0% 0% / .5) /* #00c3ff with 50% opacity */
    hwb(194, 0%, 0%, .5); /* with comma-separated values */

### Values

Functional notation: `hwb[a](H W B[/ A])`  
`H` (hue) is an [`<angle>`](../angle) of the color circle given in `deg`s, `rad`s, `grad`s, or `turn`s in [CSS Color Module Level 4](https://drafts.csswg.org/css-color/#the-hsl-notation). When written as a unitless [`<number>`](../number), it is interpreted as degrees, as specified in [CSS Color Module Level 3](https://drafts.csswg.org/css-color-3/#hsl-color). By definition, red=0deg=360deg, with the other colors spread around the circle, so green=120deg, blue=240deg, etc. As an `<angle>`, it implicitly wraps around such that -120deg=240deg, 480deg=120deg, -1turn=1turn, etc.

`W` (whiteness) specifies the amount of white to mix in, as a percentage from 0% (no whiteness) to 100% (full whiteness).

`B` (blackness) specifies the amount of black to mix in, also from 0% (no blackness) to 100% (full blackness).

`A` (alpha) can be a [`<number>`](../number) between `0` and `1`, or a [`<percentage>`](../percentage), where the number `1` corresponds to `100%` (full opacity).

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-color/#the-hwb-notation">CSS Color Module Level 4</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `css.types.color.hwb`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

The `hwb()` value has yet to be implemented in any browser. [Mozilla bug: 1352755](https://bugzilla.mozilla.org/show_bug.cgi?id=1352755)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/hwb()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/hwb()</a>
