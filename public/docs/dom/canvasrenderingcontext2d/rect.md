# CanvasRenderingContext2D.rect()

The ` CanvasRenderingContext2D``.rect() ` method of the Canvas 2D API adds a rectangle to the current path.

Like other methods that modify the current path, this method does not directly render anything. To draw the rectangle onto a canvas, you can use the [`fill()`](fill) or [`stroke()`](stroke) methods.

**Note:** To both create and render a rectangle in one step, use the [`fillRect()`](fillrect) or [`strokeRect()`](strokerect) methods.

## Syntax

    void ctx.rect(x, y, width, height);

The `rect()` method creates a rectangular path whose starting point is at `(x, y)` and whose size is specified by `width` and `height`.

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

### Drawing a rectangle

This example creates a rectangular path using the `rect()` method. The path is then rendered using the `fill()` method.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The rectangle's corner is located at (10, 20). It has a width of 150 and a height of 100.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    ctx.rect(10, 20, 150, 100);
    ctx.fill();

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-rect">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.rect' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`rect`

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
- [`CanvasRenderingContext2D.fillRect`](fillrect)
- [`CanvasRenderingContext2D.strokeRect()`](strokerect)
- [`CanvasRenderingContext2D.fill()`](fill)
- [`CanvasRenderingContext2D.stroke()`](stroke)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/rect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/rect</a>
