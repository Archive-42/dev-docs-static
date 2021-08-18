# CanvasRenderingContext2D.resetTransform()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The ` CanvasRenderingContext2D``.resetTransform() ` method of the Canvas 2D API resets the current transform to the identity matrix.

## Syntax

    void ctx.resetTransform();

## Examples

### Resetting the matrix

This example draws a rotated rectangle after modifying the matrix, and then resets the matrix using the `resetTransform()` method.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The [`rotate()`](rotate) method rotates the transformation matrix by 45°. The [`fillRect()`](fillrect) method draws a filled rectangle, adjusted according to that matrix.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Draw a rotated rectangle
    ctx.rotate(45 * Math.PI / 180);
    ctx.fillRect(60, 0, 100, 30);

    // Reset transformation matrix to the identity matrix
    ctx.resetTransform();

#### Result

### Continuing with a regular matrix

Whenever you're done drawing transformed shapes, you should call `resetTransform()` before rendering anything else. In this example, the first two shapes are drawn with a skew transformation, and the last two are drawn with the identity (regular) transformation.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Skewed rectangles
    ctx.transform(1, 0, 1.7, 1, 0, 0);
    ctx.fillStyle = 'gray';
    ctx.fillRect(40, 40, 50, 20);
    ctx.fillRect(40, 90, 50, 20);

    // Non-skewed rectangles
    ctx.resetTransform();
    ctx.fillStyle = 'red';
    ctx.fillRect(40, 40, 50, 20);
    ctx.fillRect(40, 90, 50, 20);

#### Result

The <span style="color: gray;">skewed rectangles are gray</span>, and the <span style="color: red;">non-skewed rectangles are red</span>.

## Polyfill

You can also use the [`setTransform()`](settransform) method to reset the current transform to the identity matrix, like so:

    ctx.setTransform(1, 0, 0, 1, 0, 0);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-resettransform">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.resetTransform' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`resetTransform`

31

79

36

No

18

10.1

4.4

31

36

18

10.3

2.0

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/resetTransform" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/resetTransform</a>
