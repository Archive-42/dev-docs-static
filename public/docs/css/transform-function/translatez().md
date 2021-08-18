# translateZ()

The `translateZ()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](../css_functions) repositions an element along the z-axis in 3D space, i.e., closer to or farther away from the viewer. Its result is a [`<transform-function>`](../transform-function) data type.

This transformation is defined by a [`<length>`](../length) which specifies how far inward or outward the element or elements move.

In the above interactive examples, `perspective: 550px;` (to create a 3D space) and `transform-style: preserve-3d;` (so the children, the 6 sides of the cube, are also positioned in the 3D space), have been set on the cube.

**Note:** `translateZ(tz)` is equivalent to `translate3d(0, 0, tz)`.

## Syntax

    translateZ(tz)

### Values

`tz`  
A [`<length>`](../length) representing the z-component of the translating vector. A positive value moves the element towards the viewer, and a negative value farther away.

Cartesian coordinates on ℝ<sup>2</sup>

Homogeneous coordinates on ℝℙ<sup>2</sup>

Cartesian coordinates on ℝ<sup>3</sup>

Homogeneous coordinates on ℝℙ<sup>3</sup>

This transformation applies to the 3D space and can't be represented on the plane.

A translation is not a linear transformation in ℝ<sup>3</sup> and can't be represented using a Cartesian-coordinate matrix.

$\\begin{pmatrix}
1 & 0 & 0 & 0 \\\\
0 & 1 & 0 & 0 \\\\
0 & 0 & 1 & t \\\\
0 & 0 & 0 & 1 \\\\
\\end{pmatrix}$

## Examples

In this example, two boxes are created. One is positioned normally on the page, without being translated at all. The second is altered by applying perspective to create a 3D space, then moved towards the user.

### HTML

    <div>Static</div>
    <div class="moved">Moved</div>

### CSS

    div {
      position: relative;
      width: 60px;
      height: 60px;
      left: 100px;
      background-color: skyblue;
    }

    .moved {
      transform: perspective(500px) translateZ(200px);
      background-color: pink;
    }

What really matters here is the class "moved"; let's take a look at what it does. First, the `perspective()` function positions the viewer relative to the plane that lies where z=0 (in essence, the surface of the screen). A value of `500px` means the user is 500 pixels "in front of" the imagery located at z=0.

Then, the `translateZ()` function moves the element 200 pixels "outward" from the screen, toward the user. This has the effect of making the element appear larger when viewed on a 2D display, or closer when viewed using a VR headset or other 3D display device.

Note if the `perspective()` value is less than the `translateZ()` value, such as `transform: perspective(200px) translateZ(300px);` the transformed element will not be visible as it is further than the user's viewport. The smaller the difference between the perspective and translateZ values, the closer the user is to the element and the larger the translated element will seem.

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms-2/#transform-functions">CSS Transforms Level 2<br />
<span class="small">The definition of 'transform' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Adds 3D transform functions to the CSS Transforms standard.</td></tr></tbody></table>

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

`translateZ()`

1

12

3.5

\["Firefox 14 removed experimental support for [`skew()`](https://developer.mozilla.org/docs/Web/CSS/transform-function/skew), but it was reintroduced in Firefox 15.", "Before Firefox 16, the translation values of `matrix()` and `matrix3d()` could be [`<length>`](https://developer.mozilla.org/docs/Web/CSS/length)s, in addition to the standard [`<number>`](https://developer.mozilla.org/docs/Web/CSS/number)."\]

9

Internet Explorer 9 supports 2D but not 3D transforms. In version 9, mixing 2D and 3D transform functions invalidates the entire property.

10.5

3.1

2

18

4

11

3.2

1.0

`3d`

12

12

10

10

15

4

3

18

10

14

3.2

1.0

## See also

- [`transform`](../transform)
- [`<transform-function>`](../transform-function)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translateZ()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-function/translateZ()</a>
