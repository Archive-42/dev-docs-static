# ImageData.data

The readonly `ImageData.data` property returns a [`Uint8ClampedArray`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8ClampedArray) that contains the [`ImageData`](../imagedata) object's pixel data. Data is stored as a one-dimensional array in the RGBA order, with integer values between `0` and `255` (inclusive).

## Syntax

    imageData.data

## Examples

### Getting an ImageData object's pixel data

This example creates an `ImageData` object that is 100 pixels wide and 100 pixels tall, making 10,000 pixels in all. The `data` array stores four values for each pixel, making 4 x 10,000, or 40,000 values in all.

    let imageData = new ImageData(100, 100);
    console.log(imageData.data);         // Uint8ClampedArray[40000]
    console.log(imageData.data.length);  // 40000

### Filling a blank ImageData object

This example creates and fills a new `ImageData` object with colorful pixels.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

Since each pixel consists of four values within the `data` array, the `for` loop iterates by multiples of four. The values associated with each pixel are R (red), G (green), B (blue), and A (alpha), in that order.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    const imageData = ctx.createImageData(100, 100);

    // Iterate through every pixel
    for (let i = 0; i < imageData.data.length; i += 4) {
      // Percentage in the x direction, times 255
      let x = (i % 400) / 400 * 255;
      // Percentage in the y direction, times 255
      let y = Math.ceil(i / 400) / 100 * 255;

      // Modify pixel data
      imageData.data[i + 0] = x;        // R value
      imageData.data[i + 1] = y;        // G value
      imageData.data[i + 2] = 255 - x;  // B value
      imageData.data[i + 3] = 255;      // A value
    }

    // Draw image data to the canvas
    ctx.putImageData(imageData, 20, 20);

#### Result

### More examples

For more examples using `ImageData.data`, see [Pixel manipulation with canvas](../canvas_api/tutorial/pixel_manipulation_with_canvas), [`CanvasRenderingContext2D.createImageData()`](../canvasrenderingcontext2d/createimagedata), and [`CanvasRenderingContext2D.putImageData()`](../canvasrenderingcontext2d/putimagedata).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-imagedata-data">HTML Living Standard<br />
<span class="small">The definition of 'ImageData.data' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`data`

1

12

14

9

9

3.1

1

18

14

10.1

2

1.0

## See also

- [`ImageData.height`](height)
- [`ImageData.width`](width)
- [`ImageData`](../imagedata)
- [`CanvasRenderingContext2D.createImageData()`](../canvasrenderingcontext2d/createimagedata)
- [`CanvasRenderingContext2D.putImageData()`](../canvasrenderingcontext2d/putimagedata)
- [Pixel manipulation with canvas](../canvas_api/tutorial/pixel_manipulation_with_canvas)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ImageData/data" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ImageData/data</a>
