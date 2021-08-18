# CanvasRenderingContext2D.transform()

The ` CanvasRenderingContext2D``.transform() ` method of the Canvas 2D API multiplies the current transformation with the matrix described by the arguments of this method. This lets you scale, rotate, translate (move), and skew the context.

**Note:** See also the [`setTransform()`](settransform) method, which resets the current transform to the identity matrix and then invokes `transform()`.

## Syntax

    void ctx.transform(a, b, c, d, e, f);

The transformation matrix is described by: $\\begin{bmatrix}
a & c & e \\\\
b & d & f \\\\
0 & 0 & 1 \\\\
\\end{bmatrix}$

### Parameters

`a` (m11)  
Horizontal scaling. A value of `1` results in no scaling.

`b` (m12)  
Vertical skewing.

`c` (m21)  
Horizontal skewing.

`d` (m22)  
Vertical scaling. A value of `1` results in no scaling.

`e` (dx)  
Horizontal translation (moving).

`f` (dy)  
Vertical translation (moving).

## Examples

### Skewing a shape

This example skews a rectangle both vertically (`.2`) and horizontally (`.8`). Scaling and translation remain unchanged.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.transform(1, .2, .8, 1, 0, 0);
    ctx.fillRect(0, 0, 100, 100);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-transform">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.transform' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`transform`

1

12

3

9

≤12.1

3.1

1

18

4

≤12.1

2

1.0

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.setTransform()`](settransform)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/transform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/transform</a>
