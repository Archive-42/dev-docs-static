# CanvasRenderingContext2D.isPointInPath()

The ` CanvasRenderingContext2D``.isPointInPath() ` method of the Canvas 2D API reports whether or not the specified point is contained in the current path.

## Syntax

    ctx.isPointInPath(x, y [, fillRule]);
    ctx.isPointInPath(path, x, y [, fillRule]);

### Parameters

`x`  
The x-axis coordinate of the point to check, unaffected by the current transformation of the context.

`y`  
The y-axis coordinate of the point to check, unaffected by the current transformation of the context.

`fillRule`  
The algorithm by which to determine if a point is inside or outside the path.  
Possible values:

- `"nonzero"`: The [non-zero winding rule](https://en.wikipedia.org/wiki/Nonzero-rule). Default rule.
- `"evenodd"`: The [even-odd winding rule](https://en.wikipedia.org/wiki/Even%E2%80%93odd_rule).

`path`  
A [`Path2D`](../path2d) path to check against. If unspecified, the current path is used.

### Return value

[`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean)  
A Boolean, which is `true` if the specified point is contained in the current or specified path, otherwise `false`.

## Examples

### Checking a point in the current path

This example uses the `isPointInPath()` method to check if a point is within the current path.

#### HTML

    <canvas id="canvas"></canvas>
    <p>In path: <code id="result">false</code></p>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    const result = document.getElementById('result');

    ctx.rect(10, 10, 100, 100);
    ctx.fill();
    result.innerText = ctx.isPointInPath(30, 70);

#### Result

### Checking a point in the specified path

Whenever you move the mouse, this example checks whether the cursor is in a circular `Path2D` path. If yes, the circle becomes green, otherwise it is red.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    // Create circle
    const circle = new Path2D();
    circle.arc(150, 75, 50, 0, 2 * Math.PI);
    ctx.fillStyle = 'red';
    ctx.fill(circle);

    // Listen for mouse moves
    canvas.addEventListener('mousemove', function(event) {
      // Check whether point is inside circle
      if (ctx.isPointInPath(circle, event.offsetX, event.offsetY)) {
        ctx.fillStyle = 'green';
      }
      else {
        ctx.fillStyle = 'red';
      }

      // Draw circle
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      ctx.fill(circle);
    });

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-ispointinpath">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.isPointInPath' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`isPointInPath`

1

12

2

9

≤12.1

3.1

1

18

4

≤12.1

2

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

### Gecko-specific note

- Prior to Gecko 7.0 (Firefox 7.0 / Thunderbird 7.0 / SeaMonkey 2.4), this method incorrectly failed to multiply the specified point's coordinates by the current transformation matrix before comparing it to the path. Now this method works correctly even if the context is rotated, scaled, or otherwise transformed.

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/isPointInPath" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/isPointInPath</a>
