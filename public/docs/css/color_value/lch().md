# lch()

The `lch()` functional notation expresses a given color in the LCH color space. It has the same L axis as [`lab()`](<lab()>), but uses polar coordinates C (Chroma) and H (Hue).

## Syntax

    lch(29.2345% 44.2 27);
    lch(52.2345% 72.2 56.2);
    lch(52.2345% 72.2 56.2 / .5);

### Values

Functional notation: `lab(L C H [/ A])`  
`L` specifies the CIE Lightness, and is a [`<percentage>`](../percentage) between `0%` representing black and `100%` representing white.

The second argument `C` is the chroma (roughly representing the "amount of color"). Its minimum useful value is 0, while its maximum is theoretically unbounded (but in practice does not exceed 230).

The third argument `H` is the hue angle. `0deg` points along the positive "a" axis (toward purplish red), `90deg` points along the positive "b" axis (toward mustard yellow), `180deg` points along the negative "a" axis (toward greenish cyan), and `270deg` points along the negative "b" axis (toward sky blue).

`A` (alpha) can be a [`<number>`](../number) between `0` and `1`, or a [`<percentage>`](../percentage), where the number `1` corresponds to `100%` (full opacity).

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-color/#lab-colors">CSS Color Module Level 4</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `css.types.color.lab`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [LCH colors in CSS: what, why, and how?](https://lea.verou.me/2020/04/lch-colors-in-css-what-why-and-how/)
- [Safari Technology Preview 122 release notes](https://webkit.org/blog/11577/release-notes-for-safari-technology-preview-122/): includes `lch()` and [`lab()`](<lab()>) colors.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/lch()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/lch()</a>
