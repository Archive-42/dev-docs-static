# CanvasRenderingContext2D.arc()

The ` CanvasRenderingContext2D``.arc() ` method of the [Canvas 2D API](../canvasrenderingcontext2d) adds a circular arc to the current sub-path.

## Syntax

    void ctx.arc(x, y, radius, startAngle, endAngle [, counterclockwise]);

The `arc()` method creates a circular arc centered at `(x, y)` with a radius of `radius`. The path starts at `startAngle`, ends at `endAngle`, and travels in the direction given by `counterclockwise` (defaulting to clockwise).

### Parameters

`x`  
The horizontal coordinate of the arc's center.

`y`  
The vertical coordinate of the arc's center.

`radius`  
The arc's radius. Must be positive.

`startAngle`  
The angle at which the arc starts in radians, measured from the positive x-axis.

`endAngle`  
The angle at which the arc ends in radians, measured from the positive x-axis.

`counterclockwise` <span class="badge inline optional">Optional</span>  
An optional [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). If `true`, draws the arc counter-clockwise between the start and end angles. The default is `false` (clockwise).

## Examples

### Drawing a full circle

This example draws a complete circle with the `arc()` method.

#### HTML

    <canvas></canvas>

#### JavaScript

The arc is given an x-coordinate of 100, a y-coordinate of 75, and a radius of 50. To make a full circle, the arc begins at an angle of 0 radians (0**°**), and ends at an angle of 2π radians (360**°**).

    const canvas = document.querySelector('canvas');
    const ctx = canvas.getContext('2d');

    ctx.beginPath();
    ctx.arc(100, 75, 50, 0, 2 * Math.PI);
    ctx.stroke();

#### Result

### Different shapes demonstrated

This example draws various shapes to show what is possible with `arc()`.

    const canvas = document.querySelector('canvas');
    const ctx = canvas.getContext('2d');

    // Draw shapes
    for (let i = 0; i <= 3; i++) {
      for (let j = 0; j <= 2; j++) {
        ctx.beginPath();
        let x             = 25 + j * 50;                 // x coordinate
        let y             = 25 + i * 50;                 // y coordinate
        let radius        = 20;                          // Arc radius
        let startAngle    = 0;                           // Starting point on circle
        let endAngle      = Math.PI + (Math.PI * j) / 2; // End point on circle
        let counterclockwise = i % 2 == 1;                  // Draw counterclockwise

        ctx.arc(x, y, radius, startAngle, endAngle, counterclockwise);

        if (i > 1) {
          ctx.fill();
        } else {
          ctx.stroke();
        }
      }
    }

#### Result

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-arc">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.arc' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`arc`

1

12

1.5

9

11.6

3

1

18

4

12

1

1.0

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- Use [`CanvasRenderingContext2D.ellipse()`](ellipse) to draw an elliptical arc.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/arc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/arc</a>
