# CanvasRenderingContext2D.createImageData()

The `CanvasRenderingContext2D.createImageData()` method of the Canvas 2D API creates a new, blank [`ImageData`](../imagedata) object with the specified dimensions. All of the pixels in the new object are transparent black.

## Syntax

    ImageData ctx.createImageData(width, height);
    ImageData ctx.createImageData(imagedata);

### Parameters

`width`  
The width to give the new `ImageData` object. A negative value flips the rectangle around the vertical axis.

`height`  
The height to give the new `ImageData` object. A negative value flips the rectangle around the horizontal axis.

`imagedata`  
An existing `ImageData` object from which to copy the width and height. The image itself is **not** copied.

### Return value

A new [`ImageData`](../imagedata) object with the specified width and height. The new object is filled with transparent black pixels.

### Errors thrown

`IndexSizeError`  
Thrown if either of the `width` or `height` arguments is zero.

## Examples

### Creating a blank ImageData object

This snippet creates a blank `ImageData` object using the `createImageData()` method.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The generated object is 100 pixels wide and 50 pixels tall, making 5,000 pixels in all. Each pixel within an `ImageData` object consists of four array values, so the object's [`data`](../imagedata/data) property has a length of 4 × 5,000, or 20,000.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    const imageData = ctx.createImageData(100, 50);
    console.log(imageData);
    // ImageData { width: 100, height: 50, data: Uint8ClampedArray[20000] }

### Filling a blank ImageData object

This example creates and fills a new `ImageData` object with purple pixels.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

Since each pixel consists of four values, the `for` loop iterates by multiples of four. The array values associated with each pixel are R (red), G (green), B (blue), and A (alpha), in that order.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    const imageData = ctx.createImageData(100, 100);

    // Iterate through every pixel
    for (let i = 0; i < imageData.data.length; i += 4) {
      // Modify pixel data
      imageData.data[i + 0] = 190;  // R value
      imageData.data[i + 1] = 0;    // G value
      imageData.data[i + 2] = 210;  // B value
      imageData.data[i + 3] = 255;  // A value
    }

    // Draw image data to the canvas
    ctx.putImageData(imageData, 20, 20);

#### Result

### More examples

For more examples using `createImageData()` and the `ImageData` object, see [Pixel manipulation with canvas](../canvas_api/tutorial/pixel_manipulation_with_canvas) and [`ImageData.data`](../imagedata/data).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-createimagedata">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.createImageData' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`createImageData`

1

12

2

9

≤12.1

4

1

18

4

≤12.1

3.2

1.0

### Gecko-specific notes

- Starting with (Firefox 5.0 / Thunderbird 5.0 / SeaMonkey 2.2):
  - `createImageData()` now correctly returns at least one pixel's worth of image data if a rectangle smaller than one pixel is specified.
  - Specifying non-finite values when calling `createImageData()` now properly throws a `NOT_SUPPORTED_ERR` exception.
  - `createImageData()` now handles negative arguments in accordance with the specification, by flipping the rectangle around the appropriate axis.

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`ImageData`](../imagedata)
- [Pixel manipulation with canvas](../canvas_api/tutorial/pixel_manipulation_with_canvas)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/createImageData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/createImageData</a>
