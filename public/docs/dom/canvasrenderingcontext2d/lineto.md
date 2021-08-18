# CanvasRenderingContext2D.lineTo()

The [`CanvasRenderingContext2D`](../canvasrenderingcontext2d) method `lineTo()`, part of the Canvas 2D API, adds a straight line to the current sub-path by connecting the sub-path's last point to the specified `(x, y)` coordinates.

Like other methods that modify the current path, this method does not directly render anything. To draw the path onto a canvas, you can use the [`fill()`](fill) or [`stroke()`](stroke) methods.

## Syntax

    ctx.lineTo(x, y);

### Parameters

`x`  
The x-axis coordinate of the line's end point.

`y`  
The y-axis coordinate of the line's end point.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

## Examples

### Drawing a straight line

This example draws a straight line using the `lineTo()` method.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The line begins at (30, 50) and ends at (150, 100).

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.beginPath();       // Start a new path
    ctx.moveTo(30, 50);    // Move the pen to (30, 50)
    ctx.lineTo(150, 100);  // Draw a line to (150, 100)
    ctx.stroke();          // Render the path

#### Result

### Drawing connected lines

Each call of `lineTo()` (and similar methods) automatically adds to the current sub-path, which means that all the lines will all be stroked or filled together. This example draws a letter 'M' with a single contiguous line.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.moveTo(90, 130);
    ctx.lineTo(95, 25);
    ctx.lineTo(150, 80);
    ctx.lineTo(205, 25);
    ctx.lineTo(210, 130);
    ctx.lineWidth = 15;
    ctx.stroke();

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-lineto">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.lineTo' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`lineTo`

1

12

1.5

9

11.6

2

1

18

4

12

1

1.0

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.moveTo()`](moveto)
- [`CanvasRenderingContext2D.stroke()`](stroke)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineTo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/lineTo</a>
