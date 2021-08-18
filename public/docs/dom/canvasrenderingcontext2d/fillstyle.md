# CanvasRenderingContext2D.fillStyle

The ` CanvasRenderingContext2D``.fillStyle ` property of the [Canvas 2D API](../canvas_api) specifies the color, gradient, or pattern to use inside shapes. The default style is `#000` (black).

For more examples of fill and stroke styles, see [Applying styles and color](../canvas_api/tutorial/applying_styles_and_colors) in the [Canvas tutorial](../canvas_api/tutorial).

## Syntax

    ctx.fillStyle = color;
    ctx.fillStyle = gradient;
    ctx.fillStyle = pattern;

### Options

`color`  
A [`DOMString`](../domstring) parsed as [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) value.

`gradient`  
A [`CanvasGradient`](../canvasgradient) object (a linear or radial gradient).

`pattern`  
A [`CanvasPattern`](../canvaspattern) object (a repeating image).

## Examples

### Changing the fill color of a shape

This example applies a blue fill color to a rectangle.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.fillStyle = 'blue';
    ctx.fillRect(10, 10, 100, 100);

#### Result

### Creating multiple fill colors using loops

In this example, we use two `for` loops to draw a grid of rectangles, each having a different fill color. To achieve this, we use the two variables `i` and `j` to generate a unique RGB color for each square, and only modify the red and green values. (The blue channel has a fixed value.) By modifying the channels, you can generate all kinds of palettes.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    for (let i = 0; i < 6; i++) {
      for (let j = 0; j < 6; j++) {
        ctx.fillStyle = `rgb(
            ${Math.floor(255 - 42.5 * i)},
            ${Math.floor(255 - 42.5 * j)},
            0)`;
        ctx.fillRect(j * 25, i * 25, 25, 25);
      }
    }

The result looks like this:

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAL4AAAC+CAMAAAC8qkWvAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAHtQTFRF////VP8AVKkA/ykAKX4AKdQAKVQA9/f3+/v7zMzM1CkAfikAftQAqX4A1H4A1KkAVCkAqVQAKSkAVH4Afn4AqSkAVNQA/1QAqakAVFQAKakA/6kAKf8A1FQAfv8AflQA1NQA//8A/34A1P8Aqf8A/9QAqdQAfqkA4uLihhE7PAAAAoZJREFUeNrt3cly2zAQhGFkxSirs+9xEmfh+z9hbBLUwaUGlFQl6qH/tlTlgw6f2oOh5AtLIYQQQsgJUqdpZ55pio5+qua5Ikp9TRDlz6G/8m+Rv6tJsoMPH/5B/leVHyofVL6pvFG5owIfPnz48OHDhw8fPnz48OHDhw//hvEvVL6oPFV5ovJJ5YEKfG9+zA9bfuN12w/z9qPbfk3dfti3X3O3H7lnv9t+VDYPm4fNw+Zh87B52Dz/YfaX0Q9XfrSfHj/gw4eflf9d5afKW5XHKs9UXqnAhw8fPnz4G+LHGk/+nqf5dX7Y8hee4tflFa78lddtP7zbv3xK/vzHqbb8Vn/eo1t7R7e2/o1nf9R+dW+/dtpfpsu5/e7mWV7i3H5veNrR9m6/brT99Wgz+6fZPP7t13H7n1UeqfxSealyrvJQZXjVXePLD/jw4cOHDx8+fPjw4f8tv8wPW37j9dsv3u2XTbdfvGe/9Gc/vNsfbJ7i3X7Zdvvh3n5/88xv8JbKa5XbKi9U3qmcqRzdviv/yM3j2345ZvM4tz+46prPftn07GfePKUNvym/tB/NL85Hd8Rfzkbm9uHDhw8fPnz48OHD/3f8/W+e/APQ6/z5+0r5qHJP5b3KXZX7Ks9V9jzFj+UVrvyV122/eLd/+ZT89v5c+Y3XObph3f7g6Nq3H93hcZ/90dFd3qHx5hkeXev2o3/ZWoYr6+YJ68vWEe2Xknf2w33vx/hDg/lVt98+m4fN0/vEmXbzrB8Ksm6eSP5lcfSJ033zHDH78OHfXP71xGmiOH/KNwt8Q37k0B/+B3momza76au6u3GO9oWz5vB3b+0d9pOjZzzFbeFznFBCCCFkc/kN0Ay+rk8fjJ0AAAAASUVORK5CYII=" class="internal" /></td><td></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-fillstyle">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.fillStyle' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`fillStyle`

1

12

1.5

9

≤12.1

2

1

18

4

≤12.1

1

1.0

### WebKit/Blink-specific note

In WebKit- and Blink-based browsers, the non-standard and deprecated method `ctx.setFillColor()` is implemented in addition to this property.

    setFillColor(color, optional alpha);
    setFillColor(grayLevel, optional alpha);
    setFillColor(r, g, b, a);
    setFillColor(c, m, y, k, a);

## See also

- [Canvas API](../canvas_api)
- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- Values used by this property:
  - [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) CSS data type
  - [`CanvasGradient`](../canvasgradient) object
  - [`CanvasPattern`](../canvaspattern) object

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/fillStyle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/fillStyle</a>
