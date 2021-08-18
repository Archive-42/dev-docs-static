# hsl()

The `hsl()` functional notation expresses a given color according to its hue, saturation, and lightness components. An optional alpha component represents the color's transparency.

**Note**

CSS Colors Level 4 made some changes to `hsl()`. In browsers that support the standard [`hsla()`](<hsla()>) is an alias for `hsl()`, they accept the same parameters and behave the same way.

The Level 4 specification also allows for space-separated in addition to comma-separated values.

## Syntax

    hsl(100, 100%, 50%) /* #5f0 */
    hsl(235, 100%, 50%, .5) /* #0015ff with 50% opacity */
    hsl(235 100% 50%); /* CSS Colors 4 space-separated values */

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

`hsl()`

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

`hsl()`

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

`hsl()`

1

12

1

9

9.5

3.1

≤37

18

4

10.1

2

1.0

### Space-separated values

BCD tables only load in the browser

### Accepts alpha value

BCD tables only load in the browser

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/hsl()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/hsl()</a>
