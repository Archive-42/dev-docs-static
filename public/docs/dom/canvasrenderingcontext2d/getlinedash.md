# CanvasRenderingContext2D.getLineDash()

The `getLineDash()` method of the Canvas 2D API's [`CanvasRenderingContext2D`](../canvasrenderingcontext2d) interface gets the current line dash pattern.

## Syntax

    ctx.getLineDash();

### Return value

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of numbers that specify distances to alternately draw a line and a gap (in coordinate space units). If the number, when setting the elements, is odd, the elements of the array get copied and concatenated. For example, setting the line dash to `[5, 15, 25]` will result in getting back `[5, 15, 25, 5, 15, 25]`.

## Examples

### Getting the current line dash setting

This example demonstrates the `getLineDash()` method.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

As set by [`setLineDash()`](setlinedash), strokes consist of lines that are 10 units wide, with spaces of 20 units in between each line.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.setLineDash([10, 20]);
    console.log(ctx.getLineDash());  // [10, 20]

    // Draw a dashed line
    ctx.beginPath();
    ctx.moveTo(0, 50);
    ctx.lineTo(300, 50);
    ctx.stroke();

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-getlinedash">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.getLineDash' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`getLineDash`

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
- [`CanvasRenderingContext2D.setLineDash()`](setlinedash)
- [`CanvasRenderingContext2D.lineDashOffset`](linedashoffset)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/getLineDash" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/getLineDash</a>
