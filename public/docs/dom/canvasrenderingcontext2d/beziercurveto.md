# CanvasRenderingContext2D.bezierCurveTo()

The ` CanvasRenderingContext2D``.bezierCurveTo() ` method of the Canvas 2D API adds a cubic [Bézier curve](https://en.wikipedia.org/wiki/B%C3%A9zier_curve) to the current sub-path. It requires three points: the first two are control points and the third one is the end point. The starting point is the latest point in the current path, which can be changed using [`moveTo()`](moveto) before creating the Bézier curve.

## Syntax

    void ctx.bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y);

### Parameters

`cp1x`  
The x-axis coordinate of the first control point.

`cp1y`  
The y-axis coordinate of the first control point.

`cp2x`  
The x-axis coordinate of the second control point.

`cp2y`  
The y-axis coordinate of the second control point.

`x`  
The x-axis coordinate of the end point.

`y`  
The y-axis coordinate of the end point.

## Examples

### How bezierCurveTo works

This example shows how a cubic Bézier curve is drawn.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    // Define canvas and context
    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Define the points as {x, y}
    let start = { x: 50,    y: 20  };
    let cp1 =   { x: 230,   y: 30  };
    let cp2 =   { x: 150,   y: 80  };
    let end =   { x: 250,   y: 100 };

    // Cubic Bézier curve
    ctx.beginPath();
    ctx.moveTo(start.x, start.y);
    ctx.bezierCurveTo(cp1.x, cp1.y, cp2.x, cp2.y, end.x, end.y);
    ctx.stroke();

    // Start and end points
    ctx.fillStyle = 'blue';
    ctx.beginPath();
    ctx.arc(start.x, start.y, 5, 0, 2 * Math.PI);  // Start point
    ctx.arc(end.x, end.y, 5, 0, 2 * Math.PI);      // End point
    ctx.fill();

    // Control points
    ctx.fillStyle = 'red';
    ctx.beginPath();
    ctx.arc(cp1.x, cp1.y, 5, 0, 2 * Math.PI);  // Control point one
    ctx.arc(cp2.x, cp2.y, 5, 0, 2 * Math.PI);  // Control point two
    ctx.fill();

#### Result

In this example, the <span style="color: red;">control points are red</span> and the <span style="color: blue;">start and end points are blue</span>.

### A simple Bézier curve

This example draws a simple Bézier curve using `bezierCurveTo()`.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The curve begins at the point specified by `moveTo()`: (30, 30). The first control point is placed at (120, 160), and the second at (180, 10). The curve ends at (220, 140).

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.beginPath();
    ctx.moveTo(30, 30);
    ctx.bezierCurveTo(120,160, 180,10, 220,140);
    ctx.stroke();

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-beziercurveto">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.beziercurveto' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`bezierCurveTo`

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
- [Wikipedia article on Bézier curves](https://en.wikipedia.org/wiki/B%C3%A9zier_curve)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/bezierCurveTo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/bezierCurveTo</a>
