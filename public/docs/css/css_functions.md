# CSS Functional Notation

**CSS functional notation** is a type of [CSS value](css_values_and_units) that can represent more complex data types or invoke special data processing or calculations.

## Syntax

    selector {
      property: functional-notation( [argument]? [, argument]! );
    }

The syntax starts with the **name of the functional notation**, followed by a left parenthesis `(`. Next up are the notation argument(s), and the function is finished off with a closing parenthesis `)`.

Functions can take multiple arguments, which are formatted similarly to CSS property values. Whitespace is allowed, but they are optional inside the parentheses. In some functional notations multiple arguments are separated by commas, while others use spaces.

## Transform functions

These functions are used when the [`<transform-function>`](transform-function) CSS [data type](css_types) is used as a value of [`transform`](transform).

[`matrix()`](<transform-function/matrix()>)  
Describes a homogeneous 2D transformation matrix.

[`matrix3d()`](<transform-function/matrix3d()>)  
Describes a 3D transformation as a 4×4 homogeneous matrix.

[`perspective()`](<transform-function/perspective()>)  
Sets the distance between the user and the z=0 plane.

[`rotate()`](<transform-function/rotate()>)  
Rotates an element around a fixed point on the 2D plane.

[`rotate3d()`](<transform-function/rotate3d()>)  
Rotates an element around a fixed axis in 3D space.

[`rotatex()`](<transform-function/rotatex()>)  
Rotates an element around the horizontal axis.

[`rotatey()`](<transform-function/rotatey()>)  
Rotates an element around the vertical axis.

[`rotatez()`](<transform-function/rotatez()>)  
Rotates an element around the z-axis.

[`scale()`](<transform-function/scale()>)  
Scales an element up or down on the 2D plane.

[`scale3d()`](<transform-function/scale3d()>)  
Scales an element up or down in 3D space.

[`scalex()`](<transform-function/scalex()>)  
Scales an element up or down horizontally.

[`scaley()`](<transform-function/scaley()>)  
Scales an element up or down vertically.

[`scalez()`](<transform-function/scalez()>)  
Scales an element up or down along the z-axis.

[`skew()`](<transform-function/skew()>)  
Skews an element on the 2D plane.

[`skewx()`](<transform-function/skewx()>)  
Skews an element in the horizontal direction.

[`skewy()`](<transform-function/skewy()>)  
Skews an element in the vertical direction.

[`translate()`](<transform-function/translate()>)  
Translates an element on the 2D plane.

[`translate3d()`](<transform-function/translate3d()>)  
Translates an element in 3D space.

[`translatex()`](transform-function/translatex)  
Translates an element horizontally.

[`translatey()`](<transform-function/translatey()>)  
Translates an element vertically.

[`translatez()`](<transform-function/translatez()>)  
Translates an element along the z-axis.

## Math functions

The math functions allow CSS numeric values to be written as mathematical expressions.

[`calc()`](<calc()>)  
A math function that allows basic arithmetic to be performed on numerical CSS values.

[`clamp()`](<clamp()>)  
A comparison function that takes a minimum, central, and maximum value and represents its central calculation.

[`max()`](<max()>)  
A comparison function that represents the largest of a list of values.

[`min()`](<min()>)  
A comparison function that represents the smallest of a list of values.

<span class="page-not-created">`abs()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Takes a calculation and returns the absolute value.

<span class="page-not-created">`acos()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
An inverse trigonometric function the angle returned must be normalized to the range \[0deg, 180deg\];.

<span class="page-not-created">`asin()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
An inverse trigonometric function the angle returned must be normalized to the range \[-90deg, 90deg\].

<span class="page-not-created">`atan()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
An inverse trigonometric function the angle returned must be normalized to the range \[-90deg, 90deg\].

<span class="page-not-created">`atan2()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Contains two comma-separated calculations, A and B. A and B can resolve to any [`<number>`](number), [`<dimension>`](dimension), or [`<percentage>`](percentage), but must have the same type, or else the function is invalid.

<span class="page-not-created">`cos()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Contains a single calculation which must resolve to either a [`<number>`](number) or an [`<angle>`](angle).

<span class="page-not-created">`exp()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Contains one calculation which must resolve to a [`<number>`](number), and returns the same value as pow(e, A) as a [`<number>`](number).

<span class="page-not-created">`hypot()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Contains one or more comma-separated calculations, and returns the length of an N-dimensional vector with components equal to each of the calculations.

<span class="page-not-created">`log()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Contains one or two calculations (representing the value to be logarithmed, and the base of the logarithm, defaulting to e), which must both resolve as a [`<number>`](number), and returns the logarithm base B of the value A, as a [`<number>`](number).

<span class="page-not-created">`mod()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
A modulus function that contains two calculations A and B, and returns the difference between A and the nearest integer multiple of B either above or below A.

<span class="page-not-created">`pow()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Contains two comma-separated calculations A and B, both of which must resolve as a [`<number>`](number), and returns the result of raising A to the power of B, returning the value as a [`<number>`](number).

<span class="page-not-created">`rem()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
A modulus function that contains two calculations A and B, and returns the difference between A and the nearest integer multiple of B either above or below A.

<span class="page-not-created">`round()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Contains an optional rounding strategy, and two calculations A and B, and returns the value of A, rounded according to the rounding strategy, to the nearest integer multiple of B either above or below A.

<span class="page-not-created">`sign()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Takes a calculation and returns -1 if the numeric value is negative, +1 if the numeric value is positive, 0⁺ if the numeric value is 0⁺, and 0⁻ if the numeric value is 0⁻.

<span class="page-not-created">`sin()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Contains a single calculation which must resolve to either a [`<number>`](number) or an [`<angle>`](angle).

<span class="page-not-created">`sqrt()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Contains a single calculation which must resolve to a [`<number>`](number), and returns the square root of the value as a [`<number>`](number).

<span class="page-not-created">`tan()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Contains a single calculation which must resolve to either a [`<number>`](number) or an [`<angle>`](angle).

## Filter functions

The `<filter-function>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) represents a graphical effect that can change the appearance of an input image. It is used in the [`filter`](filter) and [`backdrop-filter`](backdrop-filter) properties.

[`blur()`](<filter-function/blur()>)  
Blurs the image.

[`brightness()`](<filter-function/brightness()>)  
Makes the image brighter or darker.

[`contrast()`](<filter-function/contrast()>)  
Increases or decreases the image's contrast.

[`drop-shadow()`](<filter-function/drop-shadow()>)  
Applies a drop shadow behind the image.

[`grayscale()`](<filter-function/grayscale()>)  
Converts the image to grayscale.

[`hue-rotate()`](<filter-function/hue-rotate()>)  
Changes the overall hue of the image.

[`invert()`](<filter-function/invert()>)  
Inverts the colors of the image.

[`opacity()`](<filter-function/opacity()>)  
Makes the image transparent.

[`saturate()`](<filter-function/saturate()>)  
Super-saturates or desaturates the input image.

[`sepia()`](<filter-function/sepia()>)  
Converts the image to sepia.

## Color functions

Functions which specify different color representations. These may be used anywhere a [`<color>`](color_value) is valid.

[`color()`](<color_value/color()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Allows a color to be specified in a particular, specified colorspace (rather than the implicit sRGB colorspace that most of the other color functions operate in).

[`color-mix()`](<color_value/color-mix()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Takes two [`color`](color_value) values and returns the result of mixing them in a given colorspace by a given amount.

[`color-contrast()`](<color_value/color-contrast()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Takes a [`color`](color_value) value and compares it to a list of other [`color`](color_value) values, selecting the one with the highest contrast from the list.

[`device-cmyk()`](<color_value/device-cmyk()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Used to express CMYK colors in a device-independent way.

[`hsl()`](<color_value/hsl()>)  
The HSL color model defines a given color according to its hue, saturation, and lightness components. An optional alpha component represents the color's transparency.

[`hsla()`](<color_value/hsla()>)  
The HSL color model defines a given color according to its hue, saturation, and lightness components. The alpha component represents the color's transparency.

[`hwb()`](<color_value/hwb()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
HWB (short for Hue-Whiteness-Blackness) is another method of specifying colors, similar to HSL.

[`lab()`](<color_value/lab()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Lab color is device-independent and specifies physical measurements of color.

[`lch()`](<color_value/lch()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
LCH color is device-independent and specifies color using polar coordinates for chroma and hue.

[`rgb()`](<color_value/rgb()>)  
The RGB color model defines a given color according to its red, green, and blue components. An optional alpha component represents the color's transparency.

[`rgba()`](<color_value/rgba()>)  
The RGB color model defines a given color according to its red, green, and blue components. The alpha component represents the color's transparency.

## Image functions

These functions may be used wherever an [`<image>`](image) is valid as the value for a property.

[`conic-gradient()`](<conic-gradient()>)  
Conic gradients transition colors progressively around a circle.

[`image()`](<image()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Defines an [`<image>`](image) in a similar fashion to the [`url()`](<url()>) function, but with added functionality including specifying the image's directionality, specifying fallback images for when the preferred image is not supported

[`image-set()`](<image-set()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
A method of letting the browser pick the most appropriate CSS image from a given set, primarily for high pixel density screens.

[`linear-gradient()`](<linear-gradient()>)  
Linear gradients transition colors progressively along an imaginary line.

[`radial-gradient()`](<radial-gradient()>)  
Radial gradients transition colors progressively from a center point (origin).

[`repeating-linear-gradient()`](<repeating-linear-gradient()>)  
Is similar to `linear-gradient()` and takes the same arguments, but it repeats the color stops infinitely in all directions so as to cover its entire container.

[`repeating-radial-gradient()`](<repeating-radial-gradient()>)  
Is similar to `radial-gradient()` and takes the same arguments, but it repeats the color stops infinitely in all directions so as to cover its entire container.

[`repeating-conic-gradient()`](<repeating-conic-gradient()>)  
Is similar to `conic-gradient()` and takes the same arguments, but it repeats the color stops infinitely in all directions so as to cover its entire container.

## Counter functions

The counter functions are generally used with the [`content`](content) property, although in theory may be used wherever a [`<string>`](string) is supported.

[`counter()`](<counter()>)  
Returns a string representing the current value of the named counter, if there is one.

[`counters()`](<counters()>)  
Enables nested counters, returning a concatenated string representing the current values of the named counters, if there are any.

## Font functions

The [`font-variant-alternates`](font-variant-alternates) property controls the use of alternate glyphs, the following functions are values for this property.

<span class="page-not-created">`stylistic()`</span>  
This function enables stylistic alternates for individual characters. The parameter is a font-specific name mapped to a number. It corresponds to the OpenType value `salt`, like `salt 2`.

<span class="page-not-created">`styleset()`</span>  
This function enables stylistic alternatives for sets of characters. The parameter is a font-specific name mapped to a number. It corresponds to the OpenType value `ssXY`, like `ss02`.

<span class="page-not-created">`character-variant()`</span>  
This function enables specific stylistic alternatives for characters. It is similar to `styleset()`, but doesn't create coherent glyphs for a set of characters; individual characters will have independent and not necessarily coherent styles. The parameter is a font-specific name mapped to a number. It corresponds to the OpenType value `cvXY`, like `cv02`.

<span class="page-not-created">`swash()`</span>  
This function enables [swash](https://en.wikipedia.org/wiki/Swash_%28typography%29) glyphs. The parameter is a font-specific name mapped to a number. It corresponds to the OpenType values `swsh` and `cswh`, like `swsh 2` and `cswh 2`.

<span class="page-not-created">`ornaments()`</span>  
This function enables ornaments, like [fleurons](https://en.wikipedia.org/wiki/Fleuron_%28typography%29) and other dingbat glyphs. The parameter is a font-specific name mapped to a number. It corresponds to the OpenType value `ornm`, like `ornm 2`.

<span class="page-not-created">`annotation()`</span>  
This function enables annotations, like circled digits or inverted characters. The parameter is a font-specific name mapped to a number. It corresponds to the OpenType value `nalt`, like `nalt 2`.

## Shape functions

The following functions may be used as values for the [`<basic-shape>`](basic-shape) data type, which is used in the [`clip-path`](clip-path), [`offset-path`](offset-path), and [`shape-outside`](shape-outside) properties.

[`circle()`](<basic-shape/circle()>)  
Defines a circle.

[`ellipse()`](<basic-shape/ellipse()>)  
Defines an ellipse.

[`inset()`](<basic-shape/inset()>)  
Defines an inset rectangle.

[`polygon()`](<basic-shape/polygon()>)  
Defines a polygon.

## Index

An A-Z reference of CSS functions defined across CSS specifications. Many functions can be used with a variety of CSS properties, for example the [calc()](<calc()>) function can be used anywhere you might use a [`<length>`](length). Other functions are specfic to certain properties. Check the individual function pages for usage examples and explanations.

### A

- [abs()](<abs()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [acos()](<acos()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [annotation()](<font-variant-alternates/annotation()>) (font)
- [asin()](<asin()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [atan()](<atan()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [atan2()](<atan2()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [attr()](<attr()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

### B

- [blur()](<filter-function/blur()>) (filter)
- [brightness()](<filter-function/brightness()>) (filter)

### C

- [calc()](<calc()>) (math)
- [character-variant()](<font-variant-alternates/character-variant()>) (font)
- [circle()](<basic-shape/circle()>) (shape)
- [clamp()](<clamp()>) (math)
- [color()](<color_value/color()>) (colors) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [conic-gradient()](<conic-gradient()>)
- [cos()](<cos()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [counter()](<counter()>)
- [counters()](<counters()>)
- [contrast()](<filter-function/contrast()>) (filter)
- [cross-fade()](<cross-fade()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [cubic-bezier()](<cubic-bezier()>)

### D

- [device-cmyk()](<color_value/device-cmyk()>) (colors) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [drop-shadow()](<filter-function/drop-shadow()>) (filter)

### E

- [element()](<element()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [env()](<env()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [ellipse()](<basic-shape/ellipse()>) (shape)
- [exp()](<exp()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

### F

- [fit-content()](<fit-content()>)
- [format()](<format()>)

### G

- [grayscale()](<filter-function/grayscale()>) (filter)

### H

- [hsl()](<color_value/hsl()>) (colors)
- [hsla()](<color_value/hsla()>) (colors)
- [hue-rotate()](<filter-function/hue-rotate()>) (filter)
- [hwb()](<color_value/hwb()>) (colors) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [hypot()](<hypot()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

### I

- [image()](<image()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [image-set()](<image-set()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [inset()](<basic-shape/inset()>) (shape)
- [invert()](<filter-function/invert()>) (filter)

### L

- [lab()](<color_value/lab()>) (colors) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [lch()](<color_value/lch()>) (colors) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [leader()](<leader()>)
- [linear-gradient()](<linear-gradient()>)
- [local()](<local()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [log()](<log()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

### M

- [matrix()](<transform-function/matrix()>) (transform)
- [matrix3d()](<transform-function/matrix3d()>) (transform)
- [max()](<max()>) (math)
- [min()](<min()>) (math)
- [minmax()](<minmax()>) (math)
- [mod()](<mod()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

### O

- [opacity()](<filter-function/opacity()>) (filter)
- [ornaments()](<font-variant-alternates/ornaments()>) (font)

### P

- [paint()](<paint()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [path()](<path()>) (shape)
- [perspective()](<transform-function/perspective()>) (transform)
- [polygon()](<basic-shape/polygon()>) (shape)
- [pow()](<pow()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

### R

- [radial-gradient()](<radial-gradient()>)
- [rem()](<rem()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [repeat()](<repeat()>)
- [repeating-linear-gradient()](<repeating-linear-gradient()>)
- [repeating-radial-gradient()](<repeating-radial-gradient()>)
- [repeating-conic-gradient()](<repeating-conic-gradient()>)
- [rgb()](<color_value/rgb()>) (colors)
- [rgba()](<color_value/rgba()>) (colors)
- [rotate()](<transform-function/rotate()>) (transform)
- [rotate3d()](<transform-function/rotate3d()>) (transform)
- [rotateX()](<transform-function/rotatex()>) (transform)
- [rotateY()](<transform-function/rotatey()>) (transform)
- [rotateZ()](<transform-function/rotatez()>) (transform)
- [round()](<round()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

### S

- [saturate()](<filter-function/saturate()>) (filter)
- [scale()](<transform-function/scale()>) (transform)
- [scale3d()](<transform-function/scale3d()>) (transform)
- [scaleX()](<transform-function/scalex()>) (transform)
- [scaleY()](<transform-function/scaley()>) (transform)
- [scaleZ()](<transform-function/scalez()>) (transform)
- [sepia()](<filter-function/sepia()>) (filter)
- [sign()](<sign()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [sin()](<sin()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [skew()](<transform-function/skew()>) (transform)
- [skewX()](<transform-function/skewx()>) (transform)
- [skewY()](<transform-function/skewy()>) (transform)
- [sqrt()](<sqrt()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [steps()](<steps()>)
- [styleset()](<font-variant-alternates/styleset()>) (font)
- [stylistic()](<font-variant-alternates/stylistic()>) (font)
- [swash()](<font-variant-alternates/swash()>) (font)
- [symbols()](<symbols()>)

### T

- [tan()](<tan()>) (math) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [target-counter()](<target-counter()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [target-counters()](<target-counters()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [target-text()](<target-text()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [toggle()](<toggle()>) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [translate()](<transform-function/translate()>) (transform)
- [translate3d()](<transform-function/translate3d()>) (transform)
- [translateX()](<transform-function/translatex()>) (transform)
- [translateY()](<transform-function/translatey()>) (transform)
- [translateZ()](<transform-function/translatez()>) (transform)

### U

- [url()](<url()>)

### V

- [var()](<var()>)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-values-4/">CSS Values and Units Module Level 4</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Adds <code>toggle()</code>, <code>attr()</code>, <code>calc()</code>, <code>min()</code>, <code>max()</code>, <code>clamp()</code>, <code>round()</code>, <code>mod()</code>, <code>rem()</code>, <code>mod()</code>, <code>sin()</code>, <code>cos()</code>, <code>tan()</code>, <code>asin()</code>, <code>acos()</code>, <code>atan()</code>, <code>atan2()</code>, <code>pow()</code>, <code>sqrt()</code>, <code>hypot()</code>, <code>log()</code>, <code>exp()</code>, <code>abs()</code> and <code>sign()</code> functional notation.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-values-3/">CSS Values and Units Module Level 3</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds <code>calc()</code> functional notation.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-color/">CSS Color Module Level 4</a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds commaless syntaxes for the <code>rgb()</code>, <code>rgba()</code>, <code>hsl()</code>, and <code>hsla()</code> functional notation.<br />
Allows alpha values in <code>rgb()</code> and <code>hsl()</code>, turning <code>rgba()</code> and <code>hsla()</code> into (deprecated) aliases for them.<br />
Adds <code>hwb()</code>, <code>device-cmyk()</code>, and <code>color()</code> functions.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-color-3/">CSS Color Module Level 3</a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds <code>rgba()</code>, <code>hsl()</code>, <code>hsla()</code> functional notation.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-images-4/">CSS Images Module Level 4</a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds <code>element()</code>, <code>image()</code>, <code>image-set()</code> and <code>conic-gradient()</code> functional notation.</td></tr></tbody></table>

## See also

- [CSS Values and Units](css_values_and_units)
- [Introduction to CSS: Values and Units](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Functions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Functions</a>
