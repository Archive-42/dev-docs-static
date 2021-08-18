# CanvasRenderingContext2D.fill()

The ` CanvasRenderingContext2D``.fill() ` method of the Canvas 2D API fills the current or given path with the current [`fillStyle`](fillstyle).

## Syntax

    void ctx.fill([fillRule]);
    void ctx.fill(path [, fillRule]);

### Parameters

`fillRule`  
The algorithm by which to determine if a point is inside or outside the filling region.  
Possible values:

- `"nonzero"`: The [non-zero winding rule](https://en.wikipedia.org/wiki/Nonzero-rule). Default rule.
- `"evenodd"`: The [even-odd winding rule](https://en.wikipedia.org/wiki/Even%E2%80%93odd_rule).

`path`  
A [`Path2D`](../path2d) path to fill.

## Examples

### Filling a rectangle

This example fills a rectangle with the `fill()` method.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    ctx.rect(10, 10, 150, 100);
    ctx.fill();

#### Result

### Specifying a path and a fillRule

This example saves some intersecting lines to a Path2D object. The `fill()` method is then used to render the object to the canvas. A hole is left unfilled in the object's center by using the `"evenodd"` rule; by default (with the `"nonzero"` rule), the hole would also be filled.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Create path
    let region = new Path2D();
    region.moveTo(30, 90);
    region.lineTo(110, 20);
    region.lineTo(240, 130);
    region.lineTo(60, 130);
    region.lineTo(190, 20);
    region.lineTo(270, 90);
    region.closePath();

    // Fill path
    ctx.fillStyle = 'green';
    ctx.fill(region, 'evenodd');

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-fill">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.fill' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`fill`

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

`path_parameter`

36

≤18

31

No

23

7

37

36

31

24

7

3.0

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.fillStyle`](fillstyle)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/fill" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/fill</a>
