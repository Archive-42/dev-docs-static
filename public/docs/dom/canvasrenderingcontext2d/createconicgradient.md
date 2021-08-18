# CanvasRenderingContext2D.createConicGradient()

The `CanvasRenderingContext2D.createConicGradient()` method of the Canvas 2D API creates a gradient around a point with given coordinates.

This method returns a conic [`CanvasGradient`](../canvasgradient). To be applied to a shape, the gradient must first be assigned to the [`fillStyle`](fillstyle) or [`strokeStyle`](strokestyle) properties.

**Note:** Gradient coordinates are global, i.e., relative to the current coordinate space. When applied to a shape, the coordinates are NOT relative to the shape's coordinates.

## Syntax

    CanvasGradient ctx.createConicGradient(startAngle, x, y);

### Parameters

`startAngle`  
The angle at which to begin the gradient, in radians. Angle measurements start vertically above the centre and move around clockwise.

`x`  
The x-axis coordinate of the centre of the gradient.

`y`  
The y-axis coordinate of the centre of the gradient.

### Return value

[`CanvasGradient`](../canvasgradient)  
A conic `CanvasGradient`.

## Examples

### Filling a rectangle with a conic gradient

This example initializes a conic gradient using the `createConicGradient()` method. Five color stops between around the center coordinate are then created. Finally, the gradient is assigned to the canvas context, and is rendered to a filled rectangle.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    var canvas = document.getElementById('canvas');
    var ctx = canvas.getContext('2d');

    // Create a conic gradient
    // The start angle is 0
    // The centre position is 100, 100
    var gradient = ctx.createConicGradient(0, 100, 100);

    // Add five color stops
    gradient.addColorStop(0, "red");
    gradient.addColorStop(0.25, "orange");
    gradient.addColorStop(0.5, "yellow");
    gradient.addColorStop(0.75, "green");
    gradient.addColorStop(1, "blue");

    // Set the fill style and draw a rectangle
    ctx.fillStyle = gradient;
    ctx.fillRect(20, 20, 200, 200);

#### Rectangle result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://github.com/fserb/canvas2D/blob/95dcc7bf2f27b1fe83e12a23678666e00b992b22/spec/conic-gradient.md">Canvas 2D createConicGradient explainer.</a></td><td>Pending.</td><td>Not yet added to the HTML specification.</td></tr></tbody></table>

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

`createConicGradient`

86

No

86

No

No

No

No

86

86

No

No

No

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasGradient`](../canvasgradient)
- [`CanvasRenderingContext2D.createLinearGradient()`](createlineargradient)
- [`CanvasRenderingContext2D.createRadialGradient()`](createradialgradient)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/createConicGradient" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/createConicGradient</a>
