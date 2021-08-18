# lab()

The `lab()` functional notation expresses a given color in the CIE L\*a\*b\* color space. Lab represents the entire range of color that humans can see.

## Syntax

    lab(29.2345% 39.3825 20.0664);
    lab(52.2345% 40.1645 59.9971);
    lab(52.2345% 40.1645 59.9971 / .5);

### Values

Functional notation: `lab(L a b [/ A])`  
`L` specifies the CIE Lightness, and is a [`<percentage>`](../percentage) between `0%` representing black and `100%` representing white.

The second argument `a` is the distance along the `a` axis in the Lab colorspace.

The third argument `b` is the distance along the `b` axis in the Lab colorspace.

`A` (alpha) can be a [`<number>`](../number) between `0` and `1`, or a [`<percentage>`](../percentage), where the number `1` corresponds to `100%` (full opacity).

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-color/#lab-colors">CSS Color Module Level 4</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `css.types.color.lab`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [LCH colors in CSS: what, why, and how?](https://lea.verou.me/2020/04/lch-colors-in-css-what-why-and-how/)
- [Safari Technology Preview 122 release notes](https://webkit.org/blog/11577/release-notes-for-safari-technology-preview-122/): includes `lab()` and [`lch()`](<lch()>) colors.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/lab()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/lab()</a>
