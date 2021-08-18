# device-cmyk()

The `device-cmyk()` functional notation is used to express CMYK colors in a device independent way, specifying the cyan, magenta, yellow, and black components.

This approach to color is useful when creating material to be output to a particular printer, when the output for particular ink combinations is known. CSS processors may attempt to approximate the color, however the end result is likely to be different to the printed result.

## Syntax

    device-cmyk(0 81% 81% 30%);
    device-cmyk(0 81% 81% 30% / .5);
    device-cmyk(0 81% 81% 30% / .5, rgb(178 34 34));

### Values

Functional notation: `device-cmyk( <cmyk-component>{4} [ / <alpha-value> ]? , <color>? )`  
`<cmyk-component>` is a list of 4 [`<number>`](../number) or [`<percentage>`](../percentage) values providing the cyan, magenta, yellow, and black components of CMYK color.

` / <alpha-value>` (alpha) can be a [`<number>`](../number) between `0` and `1`, or a [`<percentage>`](../percentage), where the number `1` corresponds to `100%` (full opacity).

`<color>` is an optional fallback [`<color>`](../color_value) to use if the user agent does not know how to translate the CMYK color to RGB.

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-color/#device-cmyk">CSS Color Module Level 4</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `css.types.color.device-cmyk`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/device-cmyk()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/device-cmyk()</a>
