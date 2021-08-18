# &lt;gradient&gt;

The `<gradient>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) is a special type of [`<image>`](image) that consists of a progressive transition between two or more colors.

A CSS gradient has [no intrinsic dimensions](image#no_intrinsic); i.e., it has no natural or preferred size, nor a preferred ratio. Its concrete size will match the size of the element to which it applies.

## Syntax

The `<gradient>` data type is defined with one of the function types listed below.

#### Linear gradient

Linear gradients transition colors progressively along an imaginary line. They are generated with the [`linear-gradient()`](<linear-gradient()>) function.

#### Radial gradient

Radial gradients transition colors progressively from a center point (origin). They are generated with the [`radial-gradient()`](<radial-gradient()>) function.

#### Repeating gradient

Repeating gradients duplicate a gradient as much as necessary to fill a given area. They are generated with the [`repeating-linear-gradient()`](<repeating-linear-gradient()>) and [`repeating-radial-gradient()`](<repeating-radial-gradient()>) functions.

#### Conic gradient

Conic gradients transition colors progressively around a circle. They are generated with the [`conic-gradient()`](<conic-gradient()>) function.

## Interpolation

As with any interpolation involving colors, gradients are calculated in the alpha-premultiplied color space. This prevents unexpected shades of gray from appearing when both the color and the opacity are changing. (Be aware that older browsers may not use this behavior when using the [transparent keyword](color_value#transparent_keyword).)

## Examples

### Linear gradient example

A simple linear gradient.

    .linear-gradient {
      background: linear-gradient(to right,
          red, orange, yellow, green, blue, indigo, violet);
    }

### Radial gradient example

A simple radial gradient.

    .radial-gradient {
      background: radial-gradient(red, yellow, rgb(30, 144, 255));
    }

### Repeating gradient examples

Simple repeating linear and radial gradient examples.

    .linear-repeat {
      background: repeating-linear-gradient(to top left,
          lightpink, lightpink 5px, white 5px, white 10px);
    }

    .radial-repeat {
      background: repeating-radial-gradient(powderblue, powderblue 8px, white 8px, white 16px);
    }

### Conic gradient example

A simple conic gradient example. Note that this isn't supported widely across browser as of yet.

    .conic-gradient {
      background: conic-gradient(lightpink, white, powderblue);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-images-4/#gradients">CSS Images Module Level 4<br />
<span class="small">The definition of '&lt;gradient&gt;' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds conic-gradient</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-images-3/#gradients">CSS Images Module Level 3<br />
<span class="small">The definition of '&lt;gradient&gt;' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`gradient`

26

10

12

3.6

Gradients are limited to [`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image), [`border-image`](https://developer.mozilla.org/docs/Web/CSS/border-image), and [`mask-image`](https://developer.mozilla.org/docs/Web/CSS/mask-image).

10

12.1

11-15

15

6.1

5.1

≤37

≤37

26

18

4

Gradients are limited to [`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image), [`border-image`](https://developer.mozilla.org/docs/Web/CSS/border-image), and [`mask-image`](https://developer.mozilla.org/docs/Web/CSS/mask-image).

12.1

11-14

14

7

6

1.5

1.0

`conic-gradient`

69

79

83

75

No

56

12.1

69

69

83

79

48

12.2

10.0

`linear-gradient`

26

10

12

16

Before Firefox 36, gradients weren't applied on the pre-multiplied color space, leading to shades of grey unexpectedly appearing when used with transparency.

3.6

\["Since Firefox 42, the prefixed version of gradients can be disabled by setting `layout.css.prefixes.gradients` to `false`.", "Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right."\]

49

44

10

Internet Explorer 5.5 through 9.0 supported gradients via a proprietary filter: `-ms-filter: progid:DXImageTransform.Microsoft.Gradient()`.

12.1

11-15

Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right.

15

Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right.

6.1

5.1

\["Safari 4 was supporting an experimental `-webkit-gradient(linear,…)` function. It is more limited than the later standard version: you cannot specify both a position and an angle like in `linear-gradient()`. This old outdated syntax is still supported for compatibility purposes.", "Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right."\]

≤37

≤37

26

18

16

Before Firefox 36, gradients weren't applied on the pre-multiplied color space, leading to shades of grey unexpectedly appearing when used with transparency.

4

\["Since Firefox 42, the prefixed version of gradients can be disabled by setting `layout.css.prefixes.gradients` to `false`.", "Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right."\]

49

44

12.1

11-14

Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right.

14

Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right.

6.1

6

\["Safari 4 was supporting an experimental `-webkit-gradient(linear,…)` function. It is more limited than the later standard version: you cannot specify both a position and an angle like in `linear-gradient()`. This old outdated syntax is still supported for compatibility purposes.", "Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right."\]

1.5

1.0

`radial-gradient`

26

13

12

16

Before Firefox 36, gradients weren't applied on the pre-multiplied color space, leading to shades of grey unexpectedly appearing when used with transparency.

3.6

Since Firefox 42, the prefixed version of gradients can be disabled by setting `layout.css.prefixes.gradients` to `false`.

49

44

10

Internet Explorer 5.5 through 9.0 supported gradients via a proprietary filter: `-ms-filter: progid:DXImageTransform.Microsoft.Gradient()`.

12.1

11.6-15

15

6.1

5.1

Safari 4 was supporting an experimental `-webkit-gradient(radial,…)` function. This old outdated syntax is still supported for compatibility purposes.

≤37

≤37

26

18

16

Before Firefox 36, gradients weren't applied on the pre-multiplied color space, leading to shades of grey unexpectedly appearing when used with transparency.

4

Since Firefox 42, the prefixed version of gradients can be disabled by setting `layout.css.prefixes.gradients` to `false`.

49

44

12.1

12-14

14

6.1

6

Safari 4 was supporting an experimental `-webkit-gradient(radial,…)` function. This old outdated syntax is still supported for compatibility purposes.

1.5

1.0

`repeating-conic-gradient`

69

79

83

75

No

56

12.1

69

69

83

79

48

12.2

10.0

`repeating-linear-gradient`

26

10

12

16

Before Firefox 36, gradients weren't applied on the pre-multiplied color space, leading to shades of grey unexpectedly appearing when used with transparency.

3.6

\["Since Firefox 42, the prefixed version of gradients can be disabled by setting `layout.css.prefixes.gradients` to `false`.", "Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right."\]

49

44

10

Internet Explorer 5.5 through 9.0 supported gradients via a proprietary filter: `-ms-filter: progid:DXImageTransform.Microsoft.Gradient()`.

12.1

15

Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right.

11-15

Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right.

6.1

5.1

\["Safari 4 was supporting an experimental `-webkit-gradient(linear,…)` function. It is more limited than the later standard version: you cannot specify both a position and an angle like in `repeating-linear-gradient()`. This old outdated syntax is still supported for compatibility purposes.", "Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right."\]

≤37

≤37

26

18

16

Before Firefox 36, gradients weren't applied on the pre-multiplied color space, leading to shades of grey unexpectedly appearing when used with transparency.

4

\["Since Firefox 42, the prefixed version of gradients can be disabled by setting `layout.css.prefixes.gradients` to `false`.", "Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right."\]

49

44

12.1

14

Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right.

11-14

Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right.

6.1

6

\["Safari 4 was supporting an experimental `-webkit-gradient(linear,…)` function. It is more limited than the later standard version: you cannot specify both a position and an angle like in `repeating-linear-gradient()`. This old outdated syntax is still supported for compatibility purposes.", "Considers `<angle>` to start to the right, instead of the top. I.e. it considered an angle of `0deg` as a direction indicator pointing to the right."\]

1.5

1.0

`repeating-radial-gradient`

26

10

12

16

Before Firefox 36, gradients weren't applied on the pre-multiplied color space, leading to shades of grey unexpectedly appearing when used with transparency.

3.6

Since Firefox 42, the prefixed version of gradients can be disabled by setting `layout.css.prefixes.gradients` to `false`.

49

44

10

12.1

15

12-15

6.1

5.1

Safari 4 was supporting an experimental `-webkit-gradient(radial,…)` function. This old outdated syntax is still supported for compatibility purposes.

4.4

≤37

26

18

16

Before Firefox 36, gradients weren't applied on the pre-multiplied color space, leading to shades of grey unexpectedly appearing when used with transparency.

10

Since Firefox 42, the prefixed version of gradients can be disabled by setting `layout.css.prefixes.gradients` to `false`.

49

44

12.1

14

12-14

7

6

Safari 4 was supporting an experimental `-webkit-gradient(radial,…)` function. This old outdated syntax is still supported for compatibility purposes.

1.5

1.0

## See also

- [Using CSS gradients](css_images/using_css_gradients)
- Gradient functions: [`linear-gradient()`](<linear-gradient()>), [`radial-gradient()`](<radial-gradient()>), [`repeating-linear-gradient()`](<repeating-linear-gradient()>), [`repeating-radial-gradient()`](<repeating-radial-gradient()>), [`conic-gradient()`](<conic-gradient()>)
- [CSS Basic Data Types](css_types)
- [CSS Units and Values](css_values_and_units)
- [Introduction to CSS: Values and Units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/gradient" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/gradient</a>
