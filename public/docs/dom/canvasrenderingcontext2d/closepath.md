# CanvasRenderingContext2D.closePath()

The ` CanvasRenderingContext2D``.closePath() ` method of the Canvas 2D API attempts to add a straight line from the current point to the start of the current sub-path. If the shape has already been closed or has only one point, this function does nothing.

This method doesn't draw anything to the canvas directly. You can render the path using the [`stroke()`](stroke) or [`fill()`](fill) methods.

## Syntax

    void ctx.closePath();

## Examples

### Closing a triangle

This example creates the first two (diagonal) sides of a triangle using the `lineTo()` method. After that, the triangle's base is created with the `closePath()` method, which automatically connects the shape's first and last points.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The triangle's corners are at (20, 140), (120, 10), and (220, 140).

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.beginPath();
    ctx.moveTo(20, 140);   // Move pen to bottom-left corner
    ctx.lineTo(120, 10);   // Line to top corner
    ctx.lineTo(220, 140);  // Line to bottom-right corner
    ctx.closePath();       // Line to bottom-left corner
    ctx.stroke();

#### Result

### Closing just one sub-path

This example draws a smiley face consisting of three disconnected sub-paths.

Note: Although `closePath()` is called after all the arcs have been created, only the last arc (sub-path) gets closed.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The first two arcs create the face's eyes. The last arc creates the mouth.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.beginPath();
    ctx.arc(240, 20, 40, 0, Math.PI);
    ctx.moveTo(100, 20);
    ctx.arc(60, 20, 40, 0, Math.PI);
    ctx.moveTo(215, 80);
    ctx.arc(150, 80, 65, 0, Math.PI);
    ctx.closePath();
    ctx.lineWidth = 6;
    ctx.stroke();

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-closepath">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.closePath' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`closePath`

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
- [`CanvasRenderingContext2D.beginPath()`](beginpath)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/closePath" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/closePath</a>
