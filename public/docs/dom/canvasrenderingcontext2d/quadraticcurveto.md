# CanvasRenderingContext2D.quadraticCurveTo()

The ` CanvasRenderingContext2D``.quadraticCurveTo() ` method of the Canvas 2D API adds a quadratic [Bézier curve](https://en.wikipedia.org/wiki/B%C3%A9zier_curve) to the current sub-path. It requires two points: the first one is a control point and the second one is the end point. The starting point is the latest point in the current path, which can be changed using [`moveTo()`](moveto) before creating the quadratic Bézier curve.

## Syntax

    void ctx.quadraticCurveTo(cpx, cpy, x, y);

### Parameters

`cpx`  
The x-axis coordinate of the control point.

`cpy`  
The y-axis coordinate of the control point.

`x`  
The x-axis coordinate of the end point.

`y`  
The y-axis coordinate of the end point.

## Examples

### How quadraticCurveTo works

This example shows how a quadratic Bézier curve is drawn.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Quadratic Bézier curve
    ctx.beginPath();
    ctx.moveTo(50, 20);
    ctx.quadraticCurveTo(230, 30, 50, 100);
    ctx.stroke();

    // Start and end points
    ctx.fillStyle = 'blue';
    ctx.beginPath();
    ctx.arc(50, 20, 5, 0, 2 * Math.PI);   // Start point
    ctx.arc(50, 100, 5, 0, 2 * Math.PI);  // End point
    ctx.fill();

    // Control point
    ctx.fillStyle = 'red';
    ctx.beginPath();
    ctx.arc(230, 30, 5, 0, 2 * Math.PI);
    ctx.fill();

#### Result

In this example, the <span style="color: red;">control point is red</span> and the <span style="color: blue;">start and end points are blue</span>.

### A simple quadratic curve

This example draws a simple quadratic Bézier curve using `quadraticCurveTo()`.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The curve begins at the point specified by `moveTo()`: (20, 110). The control point is placed at (230, 150). The curve ends at (250, 20).

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.beginPath();
    ctx.moveTo(20, 110);
    ctx.quadraticCurveTo(230, 150, 250, 20);
    ctx.stroke();

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-quadraticcurveto">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.quadraticCurveTo' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`quadraticCurveTo`

1

12

1.5

9

11.6

3

1

18

4

12

1

1.0

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [Wikipedia article on Bézier curves](https://en.wikipedia.org/wiki/B%C3%A9zier_curve)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/quadraticCurveTo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/quadraticCurveTo</a>
