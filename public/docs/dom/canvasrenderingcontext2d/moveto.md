# CanvasRenderingContext2D.moveTo()

The ` CanvasRenderingContext2D``.moveTo() ` method of the Canvas 2D API begins a new sub-path at the point specified by the given `(x, y)` coordinates.

## Syntax

    void ctx.moveTo(x, y);

### Parameters

`x`  
The x-axis (horizontal) coordinate of the point.

`y`  
The y-axis (vertical) coordinate of the point.

## Examples

### Creating multiple sub-paths

This example uses `moveTo()` to create two sub-paths within a single path. Both sub-paths are then rendered with a single `stroke()` call.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The first line begins at (50, 50) and ends at (200, 50). The second line begins at (50, 90) and ends at (280, 120).

    var canvas = document.getElementById('canvas');
    var ctx = canvas.getContext('2d');

    ctx.beginPath();
    ctx.moveTo(50, 50);   // Begin first sub-path
    ctx.lineTo(200, 50);
    ctx.moveTo(50, 90);   // Begin second sub-path
    ctx.lineTo(280, 120);
    ctx.stroke();

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-moveto">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.moveTo' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`moveTo`

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
- [`CanvasRenderingContext2D.lineTo()`](lineto)
- [`CanvasRenderingContext2D.stroke()`](stroke)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/moveTo" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/moveTo</a>
