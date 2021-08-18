self.createImageBitmap()
========================

The `createImageBitmap()` method creates a bitmap from a given source, optionally cropped to contain only a portion of that source. The method exists on the global scope in both windows and workers. It accepts a variety of different image sources, and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to an [`ImageBitmap`](../imagebitmap).

Syntax
------

    const imageBitmapPromise = createImageBitmap(image[, options]);
    const imageBitmapPromise = createImageBitmap(image, sx, sy, sw, sh[, options]);

### Parameters

`image`  
An image source, which can be an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img), SVG [`<image>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/image), [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video), [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas), [`HTMLImageElement`](../htmlimageelement), [`SVGImageElement`](../svgimageelement), [`HTMLVideoElement`](../htmlvideoelement), [`HTMLCanvasElement`](../htmlcanvaselement), [`Blob`](../blob), [`ImageData`](../imagedata), [`ImageBitmap`](../imagebitmap), or [`OffscreenCanvas`](../offscreencanvas) object.

`sx`  
The x coordinate of the reference point of the rectangle from which the `ImageBitmap` will be extracted.

`sy`  
The y coordinate of the reference point of the rectangle from which the `ImageBitmap` will be extracted.

`sw`  
The width of the rectangle from which the `ImageBitmap` will be extracted. This value can be negative.

`sh`  
The height of the rectangle from which the `ImageBitmap` will be extracted. This value can be negative.

 `options` <span class="badge inline optional">Optional</span>   
An object that sets options for the image's extraction. The available options are:

-   `imageOrientation`: Specifies whether the image should be presented as is or flipped vertically. Either `none` (default) or `flipY`.
-   `premultiplyAlpha`: Specifies whether the bitmap's color channels should be premultiplied by the alpha channel. One of `none`, `premultiply`, or `default` (default).
-   `colorSpaceConversion`: Specifies whether the image should be decoded using color space conversion. Either `none` or `default` (default). The value `default` indicates that implementation-specific behavior is used.
-   `resizeWidth`: A long integer that indicates the output width.
-   `resizeHeight`: A long integer that indicates the output height.
-   `resizeQuality`: Specifies the algorithm to be used for resizing the input to match the output dimensions. One of `pixelated`, `low` (default), `medium`, or `high`.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to an [`ImageBitmap`](../imagebitmap) object containing bitmap data from the given rectangle.

Example
-------

### Creating sprites from a sprite sheet

This example loads a sprite sheet, extracts individual sprites, and then renders each sprite to the canvas. A sprite sheet is an image containing multiple smaller images, each of which you want to be able to render separately.

    var canvas = document.getElementById('myCanvas'),
    ctx = canvas.getContext('2d'),
    image = new Image();

    // Wait for the sprite sheet to load
    image.onload = function() {
      Promise.all([
        // Cut out two sprites from the sprite sheet
        createImageBitmap(image, 0, 0, 32, 32),
        createImageBitmap(image, 32, 0, 32, 32)
      ]).then(function(sprites) {
        // Draw each sprite onto the canvas
        ctx.drawImage(sprites[0], 0, 0);
        ctx.drawImage(sprites[1], 32, 32);
      });
    }

    // Load the sprite sheet from an image file
    image.src = 'sprites.png';

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#dom-createimagebitmap">HTML Living Standard<br />
<span class="small">The definition of 'createImageBitmap' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`createImageBitmap`

50

79

42

No

Yes

No

50

50

Yes

Yes

No

5.0

`options_parameter`

52

79

No

No

39

No

52

52

No

41

No

6.0

`resizeWidth_resizeHeight_resizeQuality`

54

79

No

No

Yes

No

54

54

No

Yes

No

6.0

`svgimageelement_as_source_image`

59

79

65

No

Yes

No

59

59

65

Yes

No

7.0

See also
--------

-   [`CanvasRenderingContext2D.drawImage()`](../canvasrenderingcontext2d/drawimage)
-   [`ImageData`](../imagedata)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/createImageBitmap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/createImageBitmap</a>
