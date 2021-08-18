# rgba()

The `rgba()` functional notation expresses a color according to its red, green, and blue components. An optional alpha component represents the color's transparency.

**Note**

CSS Colors Level 4 allows for space-separated in addition to comma-separated values.

## Syntax

    rgba(255,255,255,.5) /* white with 50% opacity */
    rgba(255 255 255,.5); /* CSS Colors 4 space-separated values */

### Values

Functional notation: `rgb[a](R, G, B[, A])`  
`R` (red), `G` (green), and `B` (blue) can be either [`<number>`](../number)s or [`<percentage>`](../percentage)s, where the number `255` corresponds to `100%`. `A` (alpha) can be a [`<number>`](../number) between `0` and `1`, or a [`<percentage>`](../percentage), where the number `1` corresponds to `100%` (full opacity).

Functional notation: `rgb[a](R G B[ / A])`  
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

`rgba()`

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

`rgba()`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/rgba()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/color_value/rgba()</a>
