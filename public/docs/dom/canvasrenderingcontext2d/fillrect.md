# CanvasRenderingContext2D.fillRect()

The ` CanvasRenderingContext2D``.fillRect() ` method of the Canvas 2D API draws a rectangle that is filled according to the current [`fillStyle`](fillstyle).

This method draws directly to the canvas without modifying the current path, so any subsequent [`fill()`](fill) or [`stroke()`](stroke) calls will have no effect on it.

## Syntax

    void ctx.fillRect(x, y, width, height);

The `fillRect()` method draws a filled rectangle whose starting point is at `(x, y)` and whose size is specified by `width` and `height`. The fill style is determined by the current `fillStyle` attribute.

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

### A simple filled rectangle

This example draws a filled green rectangle using the `fillRect()` method.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The rectangle's top-left corner is at (20, 10). It has a width of 150 and a height of 100.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    ctx.fillStyle = 'green';
    ctx.fillRect(20, 10, 150, 100);

#### Result

### Filling the whole canvas

This code snippet fills the entire canvas with a rectangle. This is often useful for creating a background, on top of which other things may then be drawn. To achieve this, the dimensions of the rectangle are set to equal the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element's `width` and `height` attributes.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    ctx.fillRect(0, 0, canvas.width, canvas.height);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-fillrect">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.fillRect' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`fillRect`

1

12

1.5

9

9

2

1

18

4

10.1

1

1.0

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.fillStyle`](fillstyle)
- [`CanvasRenderingContext2D.clearRect()`](clearrect)
- [`CanvasRenderingContext2D.strokeRect()`](strokerect)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/fillRect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/fillRect</a>
