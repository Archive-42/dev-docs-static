# CanvasRenderingContext2D.getImageData()

The [`CanvasRenderingContext2D`](../canvasrenderingcontext2d) method `getImageData()` of the Canvas 2D API returns an [`ImageData`](../imagedata) object representing the underlying pixel data for a specified portion of the canvas.

This method is not affected by the canvas's transformation matrix. If the specified rectangle extends outside the bounds of the canvas, the pixels outside the canvas are transparent black in the returned `ImageData` object.

**Note:** Image data can be painted onto a canvas using the [`putImageData()`](putimagedata) method.

You can find more information about `getImageData()` and general manipulation of canvas contents in [Pixel manipulation with canvas](../canvas_api/tutorial/pixel_manipulation_with_canvas).

## Syntax

    ctx.getImageData(sx, sy, sw, sh);

### Parameters

`sx`  
The x-axis coordinate of the top-left corner of the rectangle from which the `ImageData` will be extracted.

`sy`  
The y-axis coordinate of the top-left corner of the rectangle from which the `ImageData` will be extracted.

`sw`  
The width of the rectangle from which the `ImageData` will be extracted. Positive values are to the right, and negative to the left.

`sh`  
The height of the rectangle from which the `ImageData` will be extracted. Positive values are down, and negative are up.

### Return value

An [`ImageData`](../imagedata) object containing the image data for the rectangle of the canvas specified. The coordinates of the rectangle's top-left corner are `(sx, sy)`, while the coordinates of the bottom corner are `(sx + sw, sy + sh)`.

### Exceptions

`IndexSizeError`  
Thrown if either `sw` or `sh` are zero.

`SecurityError`  
The canvas contains or may contain pixels which were loaded from an origin other than the one from which the document itself was loaded. To avoid `SecurityError` being thrown in this situation, configure CORS to allow the source image to be used in this way. See [Allowing cross-origin use of images and canvas](https://developer.mozilla.org/en-US/docs/Web/HTML/CORS_enabled_image).

## Example

### Getting image data from a canvas

This example draws a rectangle, and then uses `getImageData()` to grab a portion of the canvas.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The object retrieved by `getImageData()` has a width of 200 and a height of 100, for a total of 20,000 pixels. Of those pixels, most are either transparent or taken from off the canvas; only 5,000 of them are opaque black (the color of the drawn rectangle).

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    ctx.rect(10, 10, 100, 100);
    ctx.fill();

    let imageData = ctx.getImageData(60, 60, 200, 100);
    ctx.putImageData(imageData, 150, 10);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-getimagedata">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.getImageData' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`getImageData`

1

12

2

Since Firefox 5, `getImageData` now correctly accepts rectangles that extend beyond the bounds of the canvas; pixels outside the canvas are returned as transparent black and now also returns at least one pixel's worth of image data if a rectangle smaller than one pixel is specified.

9

9.5

4

1

18

4

Since Firefox 5, `getImageData` now correctly accepts rectangles that extend beyond the bounds of the canvas; pixels outside the canvas are returned as transparent black and now also returns at least one pixel's worth of image data if a rectangle smaller than one pixel is specified.

10.1

3.2

1.0

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`ImageData`](../imagedata) object
- [`CanvasRenderingContext2D.putImageData()`](putimagedata)
- [Pixel manipulation with canvas](../canvas_api/tutorial/pixel_manipulation_with_canvas)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/getImageData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/getImageData</a>
