# CanvasRenderingContext2D.strokeStyle

The `CanvasRenderingContext2D.strokeStyle` property of the Canvas 2D API specifies the color, gradient, or pattern to use for the strokes (outlines) around shapes. The default is `#000` (black).

For more examples of stroke and fill styles, see [Applying styles and color](../canvas_api/tutorial/applying_styles_and_colors) in the [Canvas tutorial](../canvas_api/tutorial).

## Syntax

    ctx.strokeStyle = color;
    ctx.strokeStyle = gradient;
    ctx.strokeStyle = pattern;

### Options

`color`  
A [`DOMString`](../domstring) parsed as [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`<color>`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value) value.

`gradient`  
A [`CanvasGradient`](../canvasgradient) object (a linear or radial gradient).

`pattern`  
A [`CanvasPattern`](../canvaspattern) object (a repeating image).

## Examples

### Changing the stroke color of a shape

This example applies a blue stroke color to a rectangle.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    var canvas = document.getElementById('canvas');
    var ctx = canvas.getContext('2d');

    ctx.strokeStyle = 'blue';
    ctx.strokeRect(10, 10, 100, 100);

#### Result

### Creating multiple stroke colors using loops

In this example, we use two `for` loops and the [`arc()`](arc) method to draw a grid of circles, each having a different stroke color. To achieve this, we use the two variables `i` and `j` to generate a unique RGB color for each circle, and only modify the green and blue values. (The red channel has a fixed value.)

    var ctx = document.getElementById('canvas').getContext('2d');

    for (let i = 0; i < 6; i++) {
      for (let j = 0; j < 6; j++) {
        ctx.strokeStyle = `rgb(
            0,
            ${Math.floor(255 - 42.5 * i)},
            ${Math.floor(255 - 42.5 * j)})`;
        ctx.beginPath();
        ctx.arc(12.5 + j * 25, 12.5 + i * 25, 10, 0, Math.PI * 2, true);
        ctx.stroke();
      }
    }

The result looks like this:

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-strokestyle">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.strokeStyle' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`strokeStyle`

1

12

1.5

9

???12.1

2

1

18

4

???12.1

1

1.0

### WebKit/Blink-specific note

In WebKit- and Blink-based browsers, the non-standard and deprecated method `ctx.setStrokeColor()` is implemented in addition to this property.

    setStrokeColor(color, optional alpha);
    setStrokeColor(grayLevel, optional alpha);
    setStrokeColor(r, g, b, a);
    setStrokeColor(c, m, y, k, a);

## See also

- The interface defining this property: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasGradient`](../canvasgradient)
- [`CanvasPattern`](../canvaspattern)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/strokeStyle" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/strokeStyle</a>
