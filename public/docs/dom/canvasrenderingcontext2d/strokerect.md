# CanvasRenderingContext2D.strokeRect()

The ` CanvasRenderingContext2D``.strokeRect() ` method of the Canvas 2D API draws a rectangle that is stroked (outlined) according to the current [`strokeStyle`](strokestyle) and other context settings.

This method draws directly to the canvas without modifying the current path, so any subsequent [`fill()`](fill) or [`stroke()`](stroke) calls will have no effect on it.

## Syntax

    void ctx.strokeRect(x, y, width, height);

The `strokeRect()` method draws a stroked rectangle whose starting point is at `(x, y)` and whose size is specified by `width` and `height`.

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

### A simple stroked rectangle

This example draws a rectangle with a green outline using the `strokeRect()` method.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The rectangle's top-left corner is at (20, 10). It has a width of 160 and a height of 100.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    ctx.strokeStyle = 'green';
    ctx.strokeRect(20, 10, 160, 100);

#### Result

### Applying various context settings

This example draws a rectangle with a drop shadow and thick, beveled outlines.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    ctx.shadowColor = '#d53';
    ctx.shadowBlur = 20;
    ctx.lineJoin = 'bevel';
    ctx.lineWidth = 15;
    ctx.strokeStyle = '#38f';
    ctx.strokeRect(30, 30, 160, 90);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-strokerect">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.strokeRect' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`strokeRect`

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
- [`CanvasRenderingContext2D.strokeStyle`](strokestyle)
- [`CanvasRenderingContext2D.clearRect()`](clearrect)
- [`CanvasRenderingContext2D.fillRect()`](fillrect)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/strokeRect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/strokeRect</a>
