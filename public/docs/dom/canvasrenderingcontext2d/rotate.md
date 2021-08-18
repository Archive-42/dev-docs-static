# CanvasRenderingContext2D.rotate()

The ` CanvasRenderingContext2D``.rotate() ` method of the Canvas 2D API adds a rotation to the transformation matrix.

## Syntax

    void ctx.rotate(angle);

<img src="data:image/png;base64,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" class="internal" width="220" height="220" />

### Parameters

`angle`  
The rotation angle, clockwise in radians. You can use `degree * Math.PI / 180` to calculate a radian from a degree.

The rotation center point is always the canvas origin. To change the center point, you will need to move the canvas by using the [`translate()`](translate) method.

## Examples

### Rotating a shape

This example rotates a rectangle by 45°. Note that the center of rotation is the top-left corner of the canvas, and not a location relative to any shape.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Point of transform origin
    ctx.arc(0, 0, 5, 0, 2 * Math.PI);
    ctx.fillStyle = 'blue';
    ctx.fill();

    // Non-rotated rectangle
    ctx.fillStyle = 'gray';
    ctx.fillRect(100, 0, 80, 20);

    // Rotated rectangle
    ctx.rotate(45 * Math.PI / 180);
    ctx.fillStyle = 'red';
    ctx.fillRect(100, 0, 80, 20);

    // Reset transformation matrix to the identity matrix
    ctx.setTransform(1, 0, 0, 1, 0, 0);

#### Result

The <span style="color: blue;">center of rotation is blue</span>. The <span style="color: gray;">non-rotated rectangle is gray</span>, and the <span style="color: red;">rotated rectangle is red</span>.

### Rotating a shape around its center

This example rotates a shape around its center point. To do this, the following steps are applied to the matrix:

1.  First, [`translate()`](translate) moves the matrix's origin to the shape's center.
2.  `rotate()` rotates the matrix by the desired amount.
3.  Finally, `translate()` moves the matrix's origin back to its starting point. This is done by applying the values of the shape's center coordinates in a negative direction.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The shape is a rectangle with its corner at (80, 60), a width of 140, a height of 30. Its horizontal center is at (80 + 140 / 2), or 150. Its vertical center is at (60 + 30 / 2), or 75. Thus, the center point is at (150, 75).

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Non-rotated rectangle
    ctx.fillStyle = 'gray';
    ctx.fillRect(80, 60, 140, 30);

    // Matrix transformation
    ctx.translate(150, 75);
    ctx.rotate(Math.PI / 2);
    ctx.translate(-150, -75);

    // Rotated rectangle
    ctx.fillStyle = 'red';
    ctx.fillRect(80, 60, 140, 30);

#### Result

The <span style="color: gray;">non-rotated rectangle is gray</span>, and the <span style="color: red;">rotated rectangle is red</span>.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-rotate">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.rotate' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`rotate`

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

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/rotate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/rotate</a>
