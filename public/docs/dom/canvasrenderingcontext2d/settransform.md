# CanvasRenderingContext2D.setTransform()

The ` CanvasRenderingContext2D``.setTransform() ` method of the Canvas 2D API resets (overrides) the current transformation to the identity matrix, and then invokes a transformation described by the arguments of this method. This lets you scale, rotate, translate (move), and skew the context.

**Note:** See also the [`transform()`](transform) method; instead of overriding the current transform matrix, it multiplies it with a given one.

## Syntax

    ctx.setTransform(a, b, c, d, e, f);
    ctx.setTransform(matrix);

The transformation matrix is described by: $\\begin{bmatrix}
a & c & e \\\\
b & d & f \\\\
0 & 0 & 1 \\\\
\\end{bmatrix}$

### Parameters

`setTransform()` has two types of parameter that it can accept. The older type consists of several parameters representing the individual components of the transformation matrix to set:

`a` (`m11`)  
Horizontal scaling. A value of `1` results in no scaling.

`b` (`m12`)  
Vertical skewing.

`c` (`m21`)  
Horizontal skewing.

`d` (`m22`)  
Vertical scaling. A value of `1` results in no scaling.

`e` (`dx`)  
Horizontal translation (moving).

`f` (`dy`)  
Vertical translation (moving).

The newer type consists of a single parameter, `matrix`, representing a 2D transformation matrix to set (technically, a `DOMMatrixInit` object; any object will do as long as it contains the above components as properties).

## Examples

### Skewing a shape

This example skews a rectangle both vertically (`.2`) and horizontally (`.8`). Scaling and translation remain unchanged.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.setTransform(1, .2, .8, 1, 0, 0);
    ctx.fillRect(0, 0, 100, 100);

#### Result

### Retrieving and passing a DOMMatrix object

In the following example, we have two [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) elements. We apply a transform to the first one's context using the first type of `setTransform()` and draw a square on it, then retrieve the matrix from it using [`CanvasRenderingContext2D.getTransform()`](gettransform).

We then apply the retrieved matrix directly to the second canvas context by passing the `DOMMatrix` object directly to `setTransform()` (i.e. the second type), and draw a circle on it.

#### HTML

    <canvas width="240"></canvas>
    <canvas width="240"></canvas>

#### CSS

    canvas {
      border: 1px solid black;
    }

#### JavaScript

    const canvases = document.querySelectorAll('canvas');
    const ctx1 = canvases[0].getContext('2d');
    const ctx2 = canvases[1].getContext('2d');

    ctx1.setTransform(1, .2, .8, 1, 0, 0);
    ctx1.fillRect(25, 25, 50, 50);

    let storedTransform = ctx1.getTransform();
    console.log(storedTransform);

    ctx2.setTransform(storedTransform);
    ctx2.beginPath();
    ctx2.arc(50, 50, 50, 0, 2 * Math.PI);
    ctx2.fill();

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-settransform">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.setTransform' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`setTransform`

1

12

3

9

≤12.1

4

1

18

4

≤12.1

3.2

1.0

`matrix_parameter`

68

79

70

No

55

11

68

68

No

48

11

10.0

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.transform()`](transform)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/setTransform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/setTransform</a>
