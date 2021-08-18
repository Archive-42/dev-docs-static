# drop-shadow()

The `drop-shadow()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) applies a drop shadow effect to the input image. Its result is a [`<filter-function>`](../filter-function).

A drop shadow is effectively a blurred, offset version of the input image's alpha mask, drawn in a specific color and composited below the image.

**Note:** This function is somewhat similar to the [`box-shadow`](../box-shadow) property. The `box-shadow` property creates a rectangular shadow behind an element's _entire box_, while the `drop-shadow()` filter function creates a shadow that conforms to the shape (alpha channel) of the _image itself_.

## Syntax

    drop-shadow(offset-x offset-y blur-radius color)

The `drop-shadow()` function accepts a parameter of type `<shadow>` (defined in the [`box-shadow`](../box-shadow) property), with the exception that the `inset` keyword and `spread` parameters are not allowed.

### Parameters

`offset-x` `offset-y` <span class="small">(required)</span>  
Two [`<length>`](../length) values that determine the shadow offset. `offset-x` specifies the horizontal distance, where negative values place the shadow to the left of the element. `offset-y` specifies the vertical distance, where negative values place the shadow above the element. If both values are `0`, the shadow is placed directly behind the element.

`blur-radius` <span class="small">(optional)</span>  
The shadow's blur radius, specified as a [`<length>`](../length). The larger the value, the larger and more blurred the shadow becomes. If unspecified, it defaults to `0`, resulting in a sharp, unblurred edge. Negative values are not allowed.

`color` <span class="small">(optional)</span>  
The color of the shadow, specified as a [`<color>`](../color_value). If unspecified, the value of the [`color`](../color) property is used.

## Examples

### Setting a drop shadow using pixel offsets and blur radius

    /* Black shadow with 10px blur */
    drop-shadow(16px 16px 10px black)

### Setting a drop shadow using rem offsets and blur radius

    /* Reddish shadow with 1rem blur */
    drop-shadow(.5rem .5rem 1rem #e23)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/filter-effects/#funcdef-filter-drop-shadow">Filter Effects Module Level 1<br />
<span class="small">The definition of 'drop-shadow()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`drop-shadow()`

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
- CSS [`box-shadow`](../box-shadow) property
- [`blur()`](<blur()>)
- [`brightness()`](<brightness()>)
- [`contrast()`](<contrast()>)
- [`grayscale()`](<grayscale()>)
- [`hue-rotate()`](<hue-rotate()>)
- [`invert()`](<invert()>)
- [`opacity()`](<opacity()>)
- [`saturate()`](<saturate()>)
- [`sepia()`](<sepia()>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/drop-shadow()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function/drop-shadow()</a>
