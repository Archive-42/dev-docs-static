# CanvasRenderingContext2D.stroke()

The ` CanvasRenderingContext2D``.stroke() ` method of the Canvas 2D API strokes (outlines) the current or given path with the current stroke style.

Strokes are aligned to the center of a path; in other words, half of the stroke is drawn on the inner side, and half on the outer side.

The stroke is drawn using the [non-zero winding rule](https://en.wikipedia.org/wiki/Nonzero-rule), which means that path intersections will still get filled.

## Syntax

    void ctx.stroke();
    void ctx.stroke(path);

### Parameters

`path`  
A [`Path2D`](../path2d) path to stroke.

## Examples

### A simple stroked rectangle

This example creates a rectangle using the `rect()` method, and then draws it to the canvas using `stroke()`.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    ctx.rect(10, 10, 150, 100);
    ctx.stroke();

#### Result

### Re-stroking paths

Typically, you'll want to call [`beginPath()`](beginpath) for each new thing you want to stroke. If you don't, the previous sub-paths will remain part of the current path, and get stroked every time you call the `stroke()` method. In some cases, however, this may be the desired effect.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

This code strokes the first path three times, the second path two times, and the third path only once.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // First sub-path
    ctx.lineWidth = 26;
    ctx.strokeStyle = 'orange';
    ctx.moveTo(20, 20);
    ctx.lineTo(160, 20);
    ctx.stroke();

    // Second sub-path
    ctx.lineWidth = 14;
    ctx.strokeStyle = 'green';
    ctx.moveTo(20, 80);
    ctx.lineTo(220, 80);
    ctx.stroke();

    // Third sub-path
    ctx.lineWidth = 4;
    ctx.strokeStyle = 'pink';
    ctx.moveTo(20, 140);
    ctx.lineTo(280, 140);
    ctx.stroke();

#### Result

### Stroking and filling

If you want to both stroke and fill a path, the order in which you perform these actions will determine the result. In this example, the square on the left is drawn with the stroke on top of the fill. The square on the right is drawn with the fill on top of the stroke.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.lineWidth = 16;
    ctx.strokeStyle = 'red';

    // Stroke on top of fill
    ctx.beginPath();
    ctx.rect(25, 25, 100, 100);
    ctx.fill();
    ctx.stroke();

    // Fill on top of stroke
    ctx.beginPath();
    ctx.rect(175, 25, 100, 100);
    ctx.stroke();
    ctx.fill();

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-stroke">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.stroke' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`stroke`

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

`path_parameter`

36

≤18

31

No

23

7

37

36

31

24

7

3.0

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/stroke" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/stroke</a>
