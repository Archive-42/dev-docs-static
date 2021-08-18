ImageData
=========

The `ImageData` interface represents the underlying pixel data of an area of a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element. It is created using the [`ImageData()`](imagedata/imagedata) constructor or creator methods on the [`CanvasRenderingContext2D`](canvasrenderingcontext2d) object associated with a canvas: [`createImageData()`](canvasrenderingcontext2d/createimagedata) and [`getImageData()`](canvasrenderingcontext2d/getimagedata). It can also be used to set a part of the canvas by using [`putImageData()`](canvasrenderingcontext2d/putimagedata).

**Note:** This feature is available in [Web Workers](web_workers_api).

Constructors
------------

 [`ImageData()`](imagedata/imagedata) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Creates an `ImageData` object from a given [`Uint8ClampedArray`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8ClampedArray) and the size of the image it contains. If no array is given, it creates an image of a transparent black rectangle. Note that this is the most common way to create such an object in workers as [`createImageData()`](canvasrenderingcontext2d/createimagedata) is not available there.

Properties
----------

 [`ImageData.data`](imagedata/data) <span class="badge inline readonly">Read only </span>   
Is a [`Uint8ClampedArray`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Uint8ClampedArray) representing a one-dimensional array containing the data in the RGBA order, with integer values between `0` and `255` (inclusive).

 [`ImageData.height`](imagedata/height) <span class="badge inline readonly">Read only </span>   
Is an `unsigned long` representing the actual height, in pixels, of the `ImageData`.

 [`ImageData.width`](imagedata/width) <span class="badge inline readonly">Read only </span>   
Is an `unsigned long` representing the actual width, in pixels, of the `ImageData`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/canvas.html#imagedata">HTML Living Standard<br />
<span class="small">The definition of 'ImageData' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`height`

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

`width`

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

`worker_support`

Yes

≤79

25

?

?

?

Yes

Yes

25

?

?

Yes

See also
--------

-   [`CanvasRenderingContext2D`](canvasrenderingcontext2d)
-   The [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element and its associated interface, [`HTMLCanvasElement`](htmlcanvaselement).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ImageData" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ImageData</a>
