# CanvasRenderingContext2D.putImageData()

The ` CanvasRenderingContext2D``.putImageData() ` method of the Canvas 2D API paints data from the given [`ImageData`](../imagedata) object onto the canvas. If a dirty rectangle is provided, only the pixels from that rectangle are painted. This method is not affected by the canvas transformation matrix.

**Note:** Image data can be retrieved from a canvas using the [`getImageData()`](getimagedata) method.

You can find more information about `putImageData()` and general manipulation of canvas contents in the article [Pixel manipulation with canvas](../canvas_api/tutorial/pixel_manipulation_with_canvas).

## Syntax

    void ctx.putImageData(imageData, dx, dy);
    void ctx.putImageData(imageData, dx, dy, dirtyX, dirtyY, dirtyWidth, dirtyHeight);

### Parameters

`imageData`  
An [`ImageData`](../imagedata) object containing the array of pixel values.

`dx`  
Horizontal position (x coordinate) at which to place the image data in the destination canvas.

`dy`  
Vertical position (y coordinate) at which to place the image data in the destination canvas.

`dirtyX` <span class="badge inline optional">Optional</span>  
Horizontal position (x coordinate) of the top-left corner from which the image data will be extracted. Defaults to `0`.

`dirtyY` <span class="badge inline optional">Optional</span>  
Vertical position (y coordinate) of the top-left corner from which the image data will be extracted. Defaults to `0`.

`dirtyWidth` <span class="badge inline optional">Optional</span>  
Width of the rectangle to be painted. Defaults to the width of the image data.

`dirtyHeight` <span class="badge inline optional">Optional</span>  
Height of the rectangle to be painted. Defaults to the height of the image data.

### Errors thrown

`NotSupportedError`  
Thrown if any of the arguments is infinite.

`InvalidStateError`  
Thrown if the `ImageData` object's data has been detached.

## Examples

### Understanding putImageData

To understand what this algorithm does under the hood, here is an implementation on top of [`CanvasRenderingContext2D.fillRect()`](fillrect).

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    var canvas = document.getElementById('canvas');
    var ctx = canvas.getContext('2d');

    function putImageData(ctx, imageData, dx, dy,
        dirtyX, dirtyY, dirtyWidth, dirtyHeight) {
      var data = imageData.data;
      var height = imageData.height;
      var width = imageData.width;
      dirtyX = dirtyX || 0;
      dirtyY = dirtyY || 0;
      dirtyWidth = dirtyWidth !== undefined? dirtyWidth: width;
      dirtyHeight = dirtyHeight !== undefined? dirtyHeight: height;
      var limitBottom = dirtyY + dirtyHeight;
      var limitRight = dirtyX + dirtyWidth;
      for (var y = dirtyY; y < limitBottom; y++) {
        for (var x = dirtyX; x < limitRight; x++) {
          var pos = y * width + x;
          ctx.fillStyle = 'rgba(' + data[pos*4+0]
                            + ',' + data[pos*4+1]
                            + ',' + data[pos*4+2]
                            + ',' + (data[pos*4+3]/255) + ')';
          ctx.fillRect(x + dx, y + dy, 1, 1);
        }
      }
    }

    // Draw content onto the canvas
    ctx.fillRect(0, 0, 100, 100);
    // Create an ImageData object from it
    var imagedata = ctx.getImageData(0, 0, 100, 100);
    // use the putImageData function that illustrates how putImageData works
    putImageData(ctx, imagedata, 150, 0, 50, 50, 25, 25);

#### Result

### Data loss due to browser optimization

Due to the lossy nature of converting to and from premultiplied alpha color values, pixels that have just been set using `putImageData()` might be returned to an equivalent `getImageData()` as different values.

#### JavaScript

    const canvas = document.createElement("canvas");
    canvas.width = 1;
    canvas.height = 1;
    const context = canvas.getContext("2d");
    const imgData = context.getImageData(0, 0, canvas.width, canvas.height);
    const pixels = imgData.data;
    pixels[0 + 0] = 1;
    pixels[0 + 1] = 127;
    pixels[0 + 2] = 255;
    pixels[0 + 3] = 1;
    console.log("before:", pixels);
    context.putImageData(imgData, 0, 0);
    const imgData2 = context.getImageData(0, 0, canvas.width, canvas.height);
    const pixels2 = imgData2.data;
    console.log("after:", pixels2);

The output might look like:

    before: Uint8ClampedArray(4) [ 1, 127, 255, 1 ]
    after: Uint8ClampedArray(4) [ 255, 255, 255, 1 ]

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-putimagedata">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.putImageData' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`putImageData`

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

- Starting in Gecko 10.0 (Firefox 10.0 / Thunderbird 10.0 / SeaMonkey 2.7), non-finite values to any of these parameters cause the call to `putImageData()` to be silently ignored, rather than throwing an exception.
- To comply with the specification, starting with Gecko 16.0 (Firefox 16.0 / Thunderbird 16.0 / SeaMonkey 2.13), a call with an invalid number of arguments (only 3 or 7 arguments are valid), will now throw an error ([bug 762657](https://bugzilla.mozilla.org/show_bug.cgi?id=762657)).

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`ImageData`](../imagedata) object
- [`CanvasRenderingContext2D.getImageData()`](getimagedata)
- [Pixel manipulation with canvas](../canvas_api/tutorial/pixel_manipulation_with_canvas)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/putImageData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/putImageData</a>
