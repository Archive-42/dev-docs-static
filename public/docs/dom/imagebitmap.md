ImageBitmap
===========

The `ImageBitmap` interface represents a bitmap image which can be drawn to a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) without undue latency. It can be created from a variety of source objects using the [`createImageBitmap()`](windoworworkerglobalscope/createimagebitmap) factory method. `ImageBitmap` provides an asynchronous and resource efficient pathway to prepare textures for rendering in WebGL.

Properties
----------

 [`ImageBitmap.height`](imagebitmap/height) <span class="badge inline readonly">Read only </span>   
Is an `unsigned` `long` representing the height, in CSS pixels, of the `ImageData`.

 [`ImageBitmap.width`](imagebitmap/width) <span class="badge inline readonly">Read only </span>   
Is an `unsigned` `long` representing the width, in CSS pixels, of the `ImageData`.

Methods
-------

[`ImageBitmap.close()`](imagebitmap/close)  
Disposes of all graphical resources associated with an `ImageBitmap`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#imagebitmap">HTML Living Standard<br />
<span class="small">The definition of 'ImageBitmap' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`ImageBitmap`

50

79

42

No

37

No

50

50

42

37

No

5.0

`close`

52

79

46

No

37

No

52

52

46

37

No

6.0

`height`

50

79

42

No

37

No

50

50

42

37

No

5.0

`width`

50

79

42

No

37

No

50

50

42

37

No

5.0

See also
--------

-   [`WindowOrWorkerGlobalScope.createImageBitmap`](windoworworkerglobalscope/createimagebitmap)
-   [`CanvasRenderingContext2D.drawImage()`](canvasrenderingcontext2d/drawimage)
-   [`WebGLRenderingContext.texImage2D()`](webglrenderingcontext/teximage2d)
-   [`OffScreenCanvas.transferToImageBitmap()`](offscreencanvas/transfertoimagebitmap)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ImageBitmap</a>
