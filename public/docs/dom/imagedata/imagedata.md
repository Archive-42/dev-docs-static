ImageData()
===========

The `ImageData()` constructor returns a newly instantiated [`ImageData`](../imagedata) object built from the typed array given and having the specified width and height.

This constructor is the preferred way of creating such an object in a [`Worker`](../worker).

Syntax
------

    new ImageData(array, width [, height]);
    new ImageData(width, height);

### Parameters

 `array` <span class="badge inline optional">Optional</span>   
A [`Uint8ClampedArray`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8ClampedArray) containing the underlying pixel representation of the image. If no such array is given, an image with a transparent black rectangle of the specified `width` and `height` will be created.

`width`  
An unsigned long representing the width of the image.

`height`  
An unsigned long representing the height of the image. This value is optional if an array is given: the height will be inferred from the array's size and the given width.

### Return value

A new [`ImageData`](../imagedata) object.

### Errors thrown

`IndexSizeError`  
Thrown if `array` is specified, but its length is not a multiple of `(4 * width)` or `(4 * width * height)`.

Examples
--------

### Creating a blank ImageData object

This example creates an `ImageData` object that is 200 pixels wide and 100 pixels tall, containing a total of 20,000 pixels.

    let imageData = new ImageData(200, 100);
    // ImageData { width: 200, height: 100, data: Uint8ClampedArray[80000] }

### Initializing ImageData with an array

This example instantiates an `ImageData` object with pixel colors defined by an array.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

The array (`arr`) has a length of `40000`: it consists of 10,000 pixels, each of which is defined by 4 values. The `ImageData` constructor specifies a `width` of `200` for the new object, so its `height` defaults to 10,000 divided by 200, which is `50`.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    const arr = new Uint8ClampedArray(40000);

    // Iterate through every pixel
    for (let i = 0; i < arr.length; i += 4) {
      arr[i + 0] = 0;    // R value
      arr[i + 1] = 190;  // G value
      arr[i + 2] = 0;    // B value
      arr[i + 3] = 255;  // A value
    }

    // Initialize a new ImageData object
    let imageData = new ImageData(arr, 200);

    // Draw image data to the canvas
    ctx.putImageData(imageData, 20, 20);

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-imagedata">HTML Living Standard<br />
<span class="small">The definition of 'ImageData()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`ImageData`

42

14

29

No

29

6.1

No

42

29

?

7

4.0

See also
--------

-   [`CanvasRenderingContext2D.createImageData()`](../canvasrenderingcontext2d/createimagedata), the creator method that can be used outside workers.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ImageData/ImageData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ImageData/ImageData</a>
