# CanvasRenderingContext2D.isPointInStroke()

The ` CanvasRenderingContext2D``.isPointInStroke() ` method of the Canvas 2D API reports whether or not the specified point is inside the area contained by the stroking of a path.

## Syntax

    ctx.isPointInStroke(x, y);
    ctx.isPointInStroke(path, x, y);

### Parameters

`x`  
The x-axis coordinate of the point to check.

`y`  
The y-axis coordinate of the point to check.

`path`  
A [`Path2D`](../path2d) path to check against. If unspecified, the current path is used.

### Return value

[`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)  
A Boolean, which is `true` if the point is inside the area contained by the stroking of a path, otherwise `false`.

## Examples

### Checking a point in the current path

This example uses the `isPointInStroke()` method to check if a point is within the area of the current path's stroke.

#### HTML

    <canvas id="canvas"></canvas>
    <p>In stroke: <code id="result">false</code></p>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    const result = document.getElementById('result');

    ctx.rect(10, 10, 100, 100);
    ctx.stroke();
    result.innerText = ctx.isPointInStroke(50, 10);

#### Result

### Checking a point in the specified path

Whenever you move the mouse, this example checks whether the cursor is in the stroke of an elliptical `Path2D` path. If yes, the ellipse's stroke becomes green, otherwise it is red.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Create ellipse
    const ellipse = new Path2D();
    ellipse.ellipse(150, 75, 40, 60, Math.PI * .25, 0, 2 * Math.PI);
    ctx.lineWidth = 25;
    ctx.strokeStyle = 'red';
    ctx.fill(ellipse);
    ctx.stroke(ellipse);

    // Listen for mouse moves
    canvas.addEventListener('mousemove', function(event) {
      // Check whether point is inside ellipse's stroke
      if (ctx.isPointInStroke(ellipse, event.offsetX, event.offsetY)) {
        ctx.strokeStyle = 'green';
      }
      else {
        ctx.strokeStyle = 'red';
      }

      // Draw ellipse
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      ctx.fill(ellipse);
      ctx.stroke(ellipse);
    });

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-ispointinstroke">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.isPointInStroke' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`isPointInStroke`

26

79

20

19-20

No

15

6.1

≤37

26

20

19-20

14

7

1.5

`path_parameter`

36

79

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/isPointInStroke" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/isPointInStroke</a>
