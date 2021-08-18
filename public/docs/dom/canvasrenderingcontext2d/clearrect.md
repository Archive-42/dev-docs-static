# CanvasRenderingContext2D.clearRect()

The ` CanvasRenderingContext2D``.clearRect() ` method of the Canvas 2D API erases the pixels in a rectangular area by setting them to transparent black.

**Note:** Be aware that `clearRect()` may cause unintended side effects if you're not [using paths properly](../canvas_api/tutorial/drawing_shapes#drawing_paths). Make sure to call [`beginPath()`](beginpath) before starting to draw new items after calling `clearRect()`.

## Syntax

    void ctx.clearRect(x, y, width, height);

The `clearRect()` method sets the pixels in a rectangular area to transparent black (`rgba(0,0,0,0)`). The rectangle's corner is at `(x, y)`, and its size is specified by `width` and `height`.

### Parameters

`x`  
The x-axis coordinate of the rectangle's starting point.

`y`  
The y-axis coordinate of the rectangle's starting point.

`width`  
The rectangle's width. Positive values are to the right, and negative to the left.

`height`  
The rectangle's height. Positive values are down, and negative are up.

## Examples

### Erasing the whole canvas

This code snippet erases the entire canvas. This is commonly required at the start of each frame in an animation. The dimensions of the cleared area are set to equal the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element's `width` and `height` attributes.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    ctx.clearRect(0, 0, canvas.width, canvas.height);

### Erasing part of a canvas

This example draws a blue triangle on top of a yellowish background. The `clearRect()` method then erases part of the canvas.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The cleared area is rectangular in shape, with its top-left corner at (10, 10). The cleared area has a width of 120 and a height of 100.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Draw yellow background
    ctx.beginPath();
    ctx.fillStyle = '#ff6';
    ctx.fillRect(0, 0, canvas.width, canvas.height);

    // Draw blue triangle
    ctx.beginPath();
    ctx.fillStyle = 'blue';
    ctx.moveTo(20, 20);
    ctx.lineTo(180, 20);
    ctx.lineTo(130, 130);
    ctx.closePath();
    ctx.fill();

    // Clear part of the canvas
    ctx.clearRect(10, 10, 120, 100);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-clearrect">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.clearRect' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`clearRect`

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
- [`CanvasRenderingContext2D.fillRect()`](fillrect)
- [`CanvasRenderingContext2D.strokeRect()`](strokerect)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/clearRect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/clearRect</a>
