# blur()

The `blur()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) applies a [Gaussian blur](https://en.wikipedia.org/wiki/Gaussian_blur) to the input image. Its result is a [`<filter-function>`](../filter-function).

## Syntax

    blur(radius)

### Parameters

`radius`  
The radius of the blur, specified as a [`<length>`](../length). It defines the value of the standard deviation to the Gaussian function, i.e., how many pixels on the screen blend into each other; thus, a larger value will create more blur. A value of `0` leaves the input unchanged. The lacuna value for interpolation is `0`.

## Examples

### Setting a blur with pixels and with rem

    blur(0)        /* No effect */
    blur(8px)      /* Blur with 8px radius */
    blur(1.17rem)  /* Blur with 1.17rem radius */

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/filter-effects/#funcdef-filter-blur">Filter Effects Module Level 1<br />
<span class="small">The definition of 'blur()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`blur()`

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
- [`brightness()`](<brightness()>)
- [`contrast()`](<contrast()>)
- [`drop-shadow()`](<drop-shadow()>)
- [`grayscale()`](<grayscale()>)
- [`hue-rotate()`](<hue-rotate()>)
- [`invert()`](<invert()>)
- [`opacity()`](<opacity()>)
- [`saturate()`](<saturate()>)
- [`sepia()`](<sepia()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/blur()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/blur()</a>
