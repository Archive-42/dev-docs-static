# color()

The `color()` functional notation allows a color to be specified in a particular, specified colorspace rather than the implicit sRGB colorspace that most of the other color functions operate in.

Support for a particular colorspace can be detected with the [color-gamut](../@media/color-gamut) CSS media feature.

The [`@color-profile`](../@color-profile) [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`at-rule`](../at-rule) can be used to define and names a color profile to be used in the `color()` function to specify a color.

## Syntax

    color(display-p3 1 0.5 0);
    color(display-p3 1 0.5 0 / .5);

### Values

Functional notation: `color( [ [<ident> | <dashed-ident>]? [ <number-percentage>+ | <string> ] [ / <alpha-value> ]? ] )`  
`[<ident> | <dashed-ident>]` is an optional [`<ident>`](../ident) or <span class="page-not-created">`dashed-ident`</span> denoting the colorspace. If this is an `<ident>` it denotes one of the predefined colorspaces (such as display-p3); if it is a &lt;dashed-ident&gt; it denotes a custom colorspace, defined by a [`@color-profile`](../@color-profile) rule.

`[ <number-percentage>+ | <string> ]` is either one or more [`<number>`](../number) or [`<percentage>`](../percentage) values providing the parameter values that the colorspace takes, or a [`<string>`](../string) giving the name of a color defined by the colorspace.

` / <alpha-value>` (alpha) can be a [`<number>`](../number) between `0` and `1`, or a [`<percentage>`](../percentage), where the number `1` corresponds to `100%` (full opacity).

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-color/#funcdef-color">CSS Color Module Level 4</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `css.types.color.color`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Wide Gamut Color in CSS with Display-p3](https://webkit.org/blog/10042/wide-gamut-color-in-css-with-display-p3/)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/color()</a>
