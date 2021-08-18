# CanvasRenderingContext2D.beginPath()

The ` CanvasRenderingContext2D``.beginPath() ` method of the Canvas 2D API starts a new path by emptying the list of sub-paths. Call this method when you want to create a new path.

**Note:** To create a new sub-path, i.e., one matching the current canvas state, you can use [`CanvasRenderingContext2D.moveTo()`](moveto).

## Syntax

    void ctx.beginPath();

## Examples

### Creating distinct paths

This example creates two paths, each of which contains a single line.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The `beginPath()` method is called before beginning each line, so that they may be drawn with different colors.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // First path
    ctx.beginPath();
    ctx.strokeStyle = 'blue';
    ctx.moveTo(20, 20);
    ctx.lineTo(200, 20);
    ctx.stroke();

    // Second path
    ctx.beginPath();
    ctx.strokeStyle = 'green';
    ctx.moveTo(20, 20);
    ctx.lineTo(120, 120);
    ctx.stroke();

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-beginpath">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.beginPath' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`beginPath`

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
- [`CanvasRenderingContext2D.closePath()`](closepath)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/beginPath" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/beginPath</a>
