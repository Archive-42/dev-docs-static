# CanvasRenderingContext2D.setLineDash()

The `setLineDash()` method of the Canvas 2D API's [`CanvasRenderingContext2D`](../canvasrenderingcontext2d) interface sets the line dash pattern used when stroking lines. It uses an array of values that specify alternating lengths of lines and gaps which describe the pattern.

**Note:** To return to using solid lines, set the line dash list to an empty array.

## Syntax

    ctx.setLineDash(segments);

### Parameters

`segments`  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of numbers that specify distances to alternately draw a line and a gap (in coordinate space units). If the number of elements in the array is odd, the elements of the array get copied and concatenated. For example, `[5, 15, 25]` will become `[5, 15, 25, 5, 15, 25]`. If the array is empty, the line dash list is cleared and line strokes return to being solid.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

## Examples

### Basic example

This example uses the `setLineDash()` method to draw a dashed line above a solid line.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Dashed line
    ctx.beginPath();
    ctx.setLineDash([5, 15]);
    ctx.moveTo(0, 50);
    ctx.lineTo(300, 50);
    ctx.stroke();

    // Solid line
    ctx.beginPath();
    ctx.setLineDash([]);
    ctx.moveTo(0, 100);
    ctx.lineTo(300, 100);
    ctx.stroke();

#### Result

### Some common patterns

This example illustrates a variety of common line dash patterns.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The `drawDashedLine()` function created below makes the drawing of multiple dashed lines simple. It receives a pattern array as its only parameter.

    function drawDashedLine(pattern) {
      ctx.beginPath();
      ctx.setLineDash(pattern);
      ctx.moveTo(0, y);
      ctx.lineTo(300, y);
      ctx.stroke();
      y += 20;
    }

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    let y = 15;

    drawDashedLine([]);
    drawDashedLine([1, 1]);
    drawDashedLine([10, 10]);
    drawDashedLine([20, 5]);
    drawDashedLine([15, 3, 3, 3]);
    drawDashedLine([20, 3, 3, 3, 3, 3, 3, 3]);
    drawDashedLine([12, 3, 3]);  // Equals [12, 3, 3, 12, 3, 3]

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-setlinedash">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.setLineDash' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`setLineDash`

23

12

27

11

15

6.1

≤37

25

27

14

7

1.5

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.getLineDash()`](getlinedash)
- [`CanvasRenderingContext2D.lineDashOffset`](linedashoffset)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/setLineDash" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/setLineDash</a>
