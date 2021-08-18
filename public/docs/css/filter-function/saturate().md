# saturate()

The `saturate()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) super-saturates or desaturates the input image. Its result is a [`<filter-function>`](../filter-function).

## Syntax

    saturate(amount)

### Parameters

`amount`  
The amount of the conversion, specified as a [`<number>`](../number) or a [`<percentage>`](../percentage). A value under `100%` desaturates the image, while a value over `100%` super-saturates it. A value of `0%` is completely unsaturated, while a value of `100%` leaves the input unchanged. The lacuna value for interpolation is `1`.

## Examples

### Examples of correct values for saturate()

    saturate(0)     /* Completely unsaturated */
    saturate(.4)    /* 40% saturated */
    saturate(100%)  /* No effect */
    saturate(200%)  /* Double saturation */

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/filter-effects/#funcdef-filter-saturate">Filter Effects Module Level 1<br />
<span class="small">The definition of 'saturate()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`saturate()`

53

18

In Chrome 18 to 19, the `saturate()` function only takes integers instead of decimal or percentage values. From Chrome 20, this bug is fixed.

12

12

35

49

No

Internet Explorer 4 to 9 implemented a non-standard `filter` property. The syntax was completely different from this one and is not documented here.

40

15

9.1

6

53

4.4

53

35

49

41

14

9.3

6

6.0

`svg`

No

No

35

No

No

No

No

No

35

No

No

No

## See also

- [`<filter-function>`](../filter-function)
- [`blur()`](<blur()>)
- [`brightness()`](<brightness()>)
- [`contrast()`](<contrast()>)
- [`drop-shadow()`](<drop-shadow()>)
- [`grayscale()`](<grayscale()>)
- [`hue-rotate()`](<hue-rotate()>)
- [`invert()`](<invert()>)
- [`opacity()`](<opacity()>)
- [`sepia()`](<sepia()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/saturate()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/saturate()</a>
