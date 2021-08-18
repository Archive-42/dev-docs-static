# CanvasRenderingContext2D.getTransform()

The ` CanvasRenderingContext2D``.getTransform() ` method of the Canvas 2D API retrieves the current transformation matrix being applied to the context.

## Syntax

    let storedTransform = ctx.getTransform();

### Parameters

None.

### Return value

A [`DOMMatrix`](../dommatrix) object.

The transformation matrix is described by: $\\begin{bmatrix}
a & c & e \\\\
b & d & f \\\\
0 & 0 & 1 \\\\
\\end{bmatrix}$

**Note**: The returned object is not live, so updating it will not affect the current transformation matrix, and updating the current transformation matrix will not affect an already returned `DOMMatrix`.

## Examples

In the following example, we have two [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) elements. We apply a transform to the first one's context using [`CanvasRenderingContext2D.setTransform()`](settransform) and draw a square on it, then retrieve the matrix from it using `getTransform()`.

We then apply the retrieved matrix directly to the second canvas context by passing the `DOMMatrix` object directly to `setTransform()`, and draw a circle on it.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-gettransform">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.getTransform' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`getTransform`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/getTransform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/getTransform</a>
