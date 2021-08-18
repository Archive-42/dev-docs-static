# CanvasRenderingContext2D.clip()

The ` CanvasRenderingContext2D``.clip() ` method of the Canvas 2D API turns the current or given path into the current clipping region. The previous clipping region, if any, is intersected with the current or given path to create the new clipping region.

In the image below, the red outline represents a clipping region shaped like a star. Only those parts of the checkerboard pattern that are within the clipping region get drawn.

<img src="data:image/png;base64,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" class="internal" width="220" height="220" />

**Note**: Be aware that the clipping region is only constructed from shapes added to the path. It doesn't work with shape primitives drawn directly to the canvas, such as [`fillRect()`](fillrect). Instead, you'd have to use [`rect()`](rect) to add a rectangular shape to the path before calling `clip()`.

## Syntax

    void ctx.clip([fillRule]);
    void ctx.clip(path [, fillRule]);

### Parameters

`fillRule`  
The algorithm by which to determine if a point is inside or outside the clipping region. Possible values:

- `"nonzero"`: The [non-zero winding rule](https://en.wikipedia.org/wiki/Nonzero-rule). Default rule.
- `"evenodd"`: The [even-odd winding rule](https://en.wikipedia.org/wiki/Even%E2%80%93odd_rule).

`path`  
A [`Path2D`](../path2d) path to use as the clipping region.

## Examples

### A simple clipping region

This example uses the `clip()` method to create a clipping region according to the shape of a circular arc. Two rectangles are then drawn; only those parts within the clipping region are rendered.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The clipping region is a full circle, with its center at (100, 75), and a radius of 50.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Create circular clipping region
    ctx.beginPath();
    ctx.arc(100, 75, 50, 0, Math.PI * 2);
    ctx.clip();

    // Draw stuff that gets clipped
    ctx.fillStyle = 'blue';
    ctx.fillRect(0, 0, canvas.width, canvas.height);
    ctx.fillStyle = 'orange';
    ctx.fillRect(0, 0, 100, 100);

#### Result

### Specifying a path and a fillRule

This example saves two rectangles to a Path2D object, which is then made the current clipping region using the `clip()` method. The `"evenodd"` rule creates a hole where the clipping rectangles intersect; by default (with the `"nonzero"` rule), there would be no hole.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Create clipping path
    let region = new Path2D();
    region.rect(80, 10, 20, 130);
    region.rect(40, 50, 100, 50);
    ctx.clip(region, "evenodd");

    // Draw stuff that gets clipped
    ctx.fillStyle = 'blue';
    ctx.fillRect(0, 0, canvas.width, canvas.height);

#### Result

### Creating a complex clipping region

This example uses two paths, a rectangle and a square to create a complex clipping region. The `clip()` method is called twice, first to set the current clipping region to the circle using a `Path2D` object, then again to intersect the circle clipping region with a square. The final clipping region is a shape representing the intersection of the circle and the square.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Create two clipping paths
    let circlePath = new Path2D();
    circlePath.arc( 150, 75, 75, 0, 2 * Math.PI );
    let squarePath = new Path2D();
    squarePath.rect( 85, 10, 130, 130 );

    // Set the clip to the circle
    ctx.clip(circlePath);
    // Set the clip to be the intersection of the circle and the square
    ctx.clip(squarePath);

    // Draw stuff that gets clipped
    ctx.fillStyle = 'blue';
    ctx.fillRect(0, 0, canvas.width, canvas.height);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-clip">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.clip' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`clip`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/clip" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/clip</a>
