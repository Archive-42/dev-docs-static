# hue-rotate()

The `hue-rotate()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) rotates the [hue](https://en.wikipedia.org/wiki/Hue) of an element and its contents. Its result is a [`<filter-function>`](../filter-function).

## Syntax

    hue-rotate(angle)

### Parameters

`angle`  
The relative change in hue of the input sample, specified as an [`<angle>`](../angle). A value of `0deg` leaves the input unchanged. A positive hue rotation increases the hue value, while a negative rotation decreases the hue value. The lacuna value for interpolation is `0`. There is no minimum or maximum value; `hue-rotate(Ndeg)` evaluates to `N` modulo 360.

## Examples

### Examples of correct values for hue-rotate

    hue-rotate(-90deg)  /* Same as 270deg rotation */
    hue-rotate(0deg)    /* No effect */
    hue-rotate(90deg)   /* 90deg rotation */
    hue-rotate(.5turn)  /* 180deg rotation */
    hue-rotate(405deg)  /* Same as 45deg rotation */

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/filter-effects/#funcdef-filter-hue-rotate">Filter Effects Module Level 1<br />
<span class="small">The definition of 'hue-rotate()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`hue-rotate()`

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
- [`invert()`](<invert()>)
- [`opacity()`](<opacity()>)
- [`saturate()`](<saturate()>)
- [`sepia()`](<sepia()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/hue-rotate()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/hue-rotate()</a>
