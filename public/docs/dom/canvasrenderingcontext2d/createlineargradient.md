# CanvasRenderingContext2D.createLinearGradient()

The ` CanvasRenderingContext2D``.createLinearGradient() ` method of the Canvas 2D API creates a gradient along the line connecting two given coordinates.

<img src="data:image/png;base64,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" width="264" height="121" />

This method returns a linear [`CanvasGradient`](../canvasgradient). To be applied to a shape, the gradient must first be assigned to the [`fillStyle`](fillstyle) or [`strokeStyle`](strokestyle) properties.

**Note:** Gradient coordinates are global, i.e., relative to the current coordinate space. When applied to a shape, the coordinates are NOT relative to the shape's coordinates.

## Syntax

    CanvasGradient ctx.createLinearGradient(x0, y0, x1, y1);

The `createLinearGradient()` method is specified by four parameters defining the start and end points of the gradient line.

### Parameters

`x0`  
The x-axis coordinate of the start point.

`y0`  
The y-axis coordinate of the start point.

`x1`  
The x-axis coordinate of the end point.

`y1`  
The y-axis coordinate of the end point.

### Return value

[`CanvasGradient`](../canvasgradient)  
A linear `CanvasGradient` initialized with the specified line.

## Examples

### Filling a rectangle with a linear gradient

This example initializes a linear gradient using the `createLinearGradient()` method. Three color stops between the gradient's start and end points are then created. Finally, the gradient is assigned to the canvas context, and is rendered to a filled rectangle.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    var canvas = document.getElementById('canvas');
    var ctx = canvas.getContext('2d');

    // Create a linear gradient
    // The start gradient point is at x=20, y=0
    // The end gradient point is at x=220, y=0
    var gradient = ctx.createLinearGradient(20,0, 220,0);

    // Add three color stops
    gradient.addColorStop(0, 'green');
    gradient.addColorStop(.5, 'cyan');
    gradient.addColorStop(1, 'green');

    // Set the fill style and draw a rectangle
    ctx.fillStyle = gradient;
    ctx.fillRect(20, 20, 200, 100);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-createlineargradient">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.createLinearGradient' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`createLinearGradient`

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

### Gecko-specific notes

- Starting with Gecko 2.0 (Firefox 4 / Thunderbird 3.3 / SeaMonkey 2.1), specifying non-finite values now throws `NOT_SUPPORTED_ERR` instead of `SYNTAX_ERR`.

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`CanvasRenderingContext2D.createRadialGradient()`](createradialgradient)
- [`CanvasRenderingContext2D.createConicGradient()`](createconicgradient)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/createLinearGradient" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/createLinearGradient</a>
