# hsla()

The `hsla()` functional notation expresses a given color according to its hue, saturation, and lightness components. An optional alpha component represents the color's transparency.

**Note**

The Level 4 specification allows for space-separated in addition to comma-separated values.

## Syntax

    hsla(100, 100%, 50%, 1) /* #5f0 */
    hsla(235, 100%, 50%, .5) /* #0015ff with 50% opacity */
    hsla(235 100% 50% 1); /* CSS Colors 4 space-separated values */

### Values

Functional notation: `hsl[a](H, S, L[, A])`  
`H` (hue) is an [`<angle>`](../angle) of the color circle given in `deg`s, `rad`s, `grad`s, or `turn`s in [CSS Color Module Level 4](https://drafts.csswg.org/css-color/#the-hsl-notation). When written as a unitless [`<number>`](../number), it is interpreted as degrees, as specified in [CSS Color Module Level 3](https://drafts.csswg.org/css-color-3/#hsl-color). By definition, red=0deg=360deg, with the other colors spread around the circle, so green=120deg, blue=240deg, etc. As an `<angle>`, it implicitly wraps around such that -120deg=240deg, 480deg=120deg, -1turn=1turn, etc.

`S` (saturation) and `L` (lightness) are percentages. `100%` **saturation** is completely saturated, while `0%` is completely unsaturated (gray). `100%` **lightness** is white, `0%` lightness is black, and `50%` lightness is “normal.”

`A` (alpha) can be a [`<number>`](../number) between `0` and `1`, or a [`<percentage>`](../percentage), where the number `1` corresponds to `100%` (full opacity).

Functional notation: `hsl[a](H S L[ / A])`  
CSS Colors Level 4 adds support for space-separated values in the functional notation.

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

`hsla()`

65

79

52

No

52

12.1

65

65

52

47

12.2

9.0

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

`hsla()`

1

12

3

9

10

3.1

≤37

18

4

10.1

2

1.0

### Space-separated values

BCD tables only load in the browser

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/hsla()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/hsla()</a>
