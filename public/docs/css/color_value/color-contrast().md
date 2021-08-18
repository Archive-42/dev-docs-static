# color-contrast()

The `color-contrast()` functional notation takes a [`color`](../color_value) value and compares it to a list of other [`color`](../color_value) values, selecting the one with the highest contrast from the list.

## Syntax

    color-contrast(wheat vs tan, sienna, #d2691e)
    color-contrast(#008080 vs olive, var(--myColor), #d2691e)

### Values

Functional notation: `color-contrast( <color> vs <color>#{2,} )`  
`<color>` is any valid [`color`](../color_value).

`<color>#{2,}` is a comma-separated list of color values to compare with the first value.

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-color-5/#colorcontrast">CSS Color Module Level 5</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `css.types.color.color-contrast`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color-contrast()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color-contrast()</a>
