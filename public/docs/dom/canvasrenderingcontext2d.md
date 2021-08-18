# CanvasRenderingContext2D

The `CanvasRenderingContext2D` interface, part of the [Canvas API](canvas_api), provides the 2D rendering context for the drawing surface of a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element. It is used for drawing shapes, text, images, and other objects.

See the interface's properties and methods in the sidebar and below. The [Canvas tutorial](canvas_api/tutorial) has more explanation, examples, and resources, as well.

## Basic example

To get a `CanvasRenderingContext2D` instance, you must first have an HTML `<canvas>` element to work with:

    <canvas id="my-house" width="300" height="300"></canvas>

To get the canvas' 2D rendering context, call [`getContext()`](htmlcanvaselement/getcontext) on the `<canvas>` element, supplying `'2d'` as the argument:

    const canvas = document.getElementById('my-house');
    const ctx = canvas.getContext('2d');

With the context in hand, you can draw anything you like. This code draws a house:

    // Set line width
    ctx.lineWidth = 10;

    // Wall
    ctx.strokeRect(75, 140, 150, 110);

    // Door
    ctx.fillRect(130, 190, 40, 60);

    // Roof
    ctx.beginPath();
    ctx.moveTo(50, 140);
    ctx.lineTo(150, 60);
    ctx.lineTo(250, 140);
    ctx.closePath();
    ctx.stroke();

The resulting drawing looks like this:

## Reference

### Drawing rectangles

There are three methods that immediately draw rectangles to the canvas.

[`CanvasRenderingContext2D.clearRect()`](canvasrenderingcontext2d/clearrect)  
Sets all pixels in the rectangle defined by starting point _(x, y)_ and size _(width, height)_ to transparent black, erasing any previously drawn content.

[`CanvasRenderingContext2D.fillRect()`](canvasrenderingcontext2d/fillrect)  
Draws a filled rectangle at _(x, y)_ position whose size is determined by _width_ and _height_.

[`CanvasRenderingContext2D.strokeRect()`](canvasrenderingcontext2d/strokerect)  
Paints a rectangle which has a starting point at _(x, y)_ and has a _w_ width and an _h_ height onto the canvas, using the current stroke style.

### Drawing text

The following methods draw text. See also the [`TextMetrics`](textmetrics) object for text properties.

[`CanvasRenderingContext2D.fillText()`](canvasrenderingcontext2d/filltext)  
Draws (fills) a given text at the given (x, y) position.

[`CanvasRenderingContext2D.strokeText()`](canvasrenderingcontext2d/stroketext)  
Draws (strokes) a given text at the given (x, y) position.

[`CanvasRenderingContext2D.measureText()`](canvasrenderingcontext2d/measuretext)  
Returns a [`TextMetrics`](textmetrics) object.

### Line styles

The following methods and properties control how lines are drawn.

[`CanvasRenderingContext2D.lineWidth`](canvasrenderingcontext2d/linewidth)  
Width of lines. Default `1.0`.

[`CanvasRenderingContext2D.lineCap`](canvasrenderingcontext2d/linecap)  
Type of endings on the end of lines. Possible values: `butt` (default), `round`, `square`.

[`CanvasRenderingContext2D.lineJoin`](canvasrenderingcontext2d/linejoin)  
Defines the type of corners where two lines meet. Possible values: `round`, `bevel`, `miter` (default).

[`CanvasRenderingContext2D.miterLimit`](canvasrenderingcontext2d/miterlimit)  
Miter limit ratio. Default `10`.

[`CanvasRenderingContext2D.getLineDash()`](canvasrenderingcontext2d/getlinedash)  
Returns the current line dash pattern array containing an even number of non-negative numbers.

[`CanvasRenderingContext2D.setLineDash()`](canvasrenderingcontext2d/setlinedash)  
Sets the current line dash pattern.

[`CanvasRenderingContext2D.lineDashOffset`](canvasrenderingcontext2d/linedashoffset)  
Specifies where to start a dash array on a line.

### Text styles

The following properties control how text is laid out.

[`CanvasRenderingContext2D.font`](canvasrenderingcontext2d/font)  
Font setting. Default value `10px sans-serif`.

[`CanvasRenderingContext2D.textAlign`](canvasrenderingcontext2d/textalign)  
Text alignment setting. Possible values: `start` (default), `end`, `left`, `right`, `center`.

[`CanvasRenderingContext2D.textBaseline`](canvasrenderingcontext2d/textbaseline)  
Baseline alignment setting. Possible values: `top`, `hanging`, `middle`, `alphabetic` (default), `ideographic`, `bottom`.

[`CanvasRenderingContext2D.direction`](canvasrenderingcontext2d/direction)  
Directionality. Possible values: `ltr`, `rtl`, `inherit` (default).

### Fill and stroke styles

Fill styling is used for colors and styles inside shapes and stroke styling is used for the lines around shapes.

[`CanvasRenderingContext2D.fillStyle`](canvasrenderingcontext2d/fillstyle)  
Color or style to use inside shapes. Default `#000` (black).

[`CanvasRenderingContext2D.strokeStyle`](canvasrenderingcontext2d/strokestyle)  
Color or style to use for the lines around shapes. Default `#000` (black).

### Gradients and patterns

[`CanvasRenderingContext2D.createConicGradient()`](canvasrenderingcontext2d/createconicgradient)  
Creates a conic gradient around a point given by coordinates represented by the parameters.

[`CanvasRenderingContext2D.createLinearGradient()`](canvasrenderingcontext2d/createlineargradient)  
Creates a linear gradient along the line given by the coordinates represented by the parameters.

[`CanvasRenderingContext2D.createRadialGradient()`](canvasrenderingcontext2d/createradialgradient)  
Creates a radial gradient given by the coordinates of the two circles represented by the parameters.

[`CanvasRenderingContext2D.createPattern()`](canvasrenderingcontext2d/createpattern)  
Creates a pattern using the specified image (a [`CanvasImageSource`](canvasimagesource)). It repeats the source in the directions specified by the repetition argument. This method returns a [`CanvasPattern`](canvaspattern).

### Shadows

[`CanvasRenderingContext2D.shadowBlur`](canvasrenderingcontext2d/shadowblur)  
Specifies the blurring effect. Default: `0`

[`CanvasRenderingContext2D.shadowColor`](canvasrenderingcontext2d/shadowcolor)  
Color of the shadow. Default: fully-transparent black.

[`CanvasRenderingContext2D.shadowOffsetX`](canvasrenderingcontext2d/shadowoffsetx)  
Horizontal distance the shadow will be offset. Default: `0`.

[`CanvasRenderingContext2D.shadowOffsetY`](canvasrenderingcontext2d/shadowoffsety)  
Vertical distance the shadow will be offset. Default: `0`.

### Paths

The following methods can be used to manipulate paths of objects.

[`CanvasRenderingContext2D.beginPath()`](canvasrenderingcontext2d/beginpath)  
Starts a new path by emptying the list of sub-paths. Call this method when you want to create a new path.

[`CanvasRenderingContext2D.closePath()`](canvasrenderingcontext2d/closepath)  
Causes the point of the pen to move back to the start of the current sub-path. It tries to draw a straight line from the current point to the start. If the shape has already been closed or has only one point, this function does nothing.

[`CanvasRenderingContext2D.moveTo()`](canvasrenderingcontext2d/moveto)  
Moves the starting point of a new sub-path to the (x, y) coordinates.

[`CanvasRenderingContext2D.lineTo()`](canvasrenderingcontext2d/lineto)  
Connects the last point in the current sub-path to the specified (x, y) coordinates with a straight line.

[`CanvasRenderingContext2D.bezierCurveTo()`](canvasrenderingcontext2d/beziercurveto)  
Adds a cubic Bézier curve to the current path.

[`CanvasRenderingContext2D.quadraticCurveTo()`](canvasrenderingcontext2d/quadraticcurveto)  
Adds a quadratic Bézier curve to the current path.

[`CanvasRenderingContext2D.arc()`](canvasrenderingcontext2d/arc)  
Adds a circular arc to the current path.

[`CanvasRenderingContext2D.arcTo()`](canvasrenderingcontext2d/arcto)  
Adds an arc to the current path with the given control points and radius, connected to the previous point by a straight line.

[`CanvasRenderingContext2D.ellipse()`](canvasrenderingcontext2d/ellipse)  
Adds an elliptical arc to the current path.

[`CanvasRenderingContext2D.rect()`](canvasrenderingcontext2d/rect)  
Creates a path for a rectangle at position (x, y) with a size that is determined by _width_ and _height_.

### Drawing paths

[`CanvasRenderingContext2D.fill()`](canvasrenderingcontext2d/fill)  
Fills the current sub-paths with the current fill style.

[`CanvasRenderingContext2D.stroke()`](canvasrenderingcontext2d/stroke)  
Strokes the current sub-paths with the current stroke style.

[`CanvasRenderingContext2D.drawFocusIfNeeded()`](canvasrenderingcontext2d/drawfocusifneeded)  
If a given element is focused, this method draws a focus ring around the current path.

[`CanvasRenderingContext2D.scrollPathIntoView()`](canvasrenderingcontext2d/scrollpathintoview)  
Scrolls the current path or a given path into the view.

[`CanvasRenderingContext2D.clip()`](canvasrenderingcontext2d/clip)  
Creates a clipping path from the current sub-paths. Everything drawn after `clip()` is called appears inside the clipping path only. For an example, see [Clipping paths](canvas_api/tutorial/compositing) in the Canvas tutorial.

[`CanvasRenderingContext2D.isPointInPath()`](canvasrenderingcontext2d/ispointinpath)  
Reports whether or not the specified point is contained in the current path.

[`CanvasRenderingContext2D.isPointInStroke()`](canvasrenderingcontext2d/ispointinstroke)  
Reports whether or not the specified point is inside the area contained by the stroking of a path.

### Transformations

Objects in the `CanvasRenderingContext2D` rendering context have a current transformation matrix and methods to manipulate it. The transformation matrix is applied when creating the current default path, painting text, shapes and [`Path2D`](path2d) objects. The methods listed below remain for historical and compatibility reasons as [`DOMMatrix`](dommatrix) objects are used in most parts of the API nowadays and will be used in the future instead.

[`CanvasRenderingContext2D.currentTransform`](canvasrenderingcontext2d/currenttransform) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Current transformation matrix ([`DOMMatrix`](dommatrix) object).

[`CanvasRenderingContext2D.getTransform()`](canvasrenderingcontext2d/gettransform)  
Retrieves the current transformation matrix being applied to the context.

[`CanvasRenderingContext2D.rotate()`](canvasrenderingcontext2d/rotate)  
Adds a rotation to the transformation matrix. The angle argument represents a clockwise rotation angle and is expressed in radians.

[`CanvasRenderingContext2D.scale()`](canvasrenderingcontext2d/scale)  
Adds a scaling transformation to the canvas units by x horizontally and by y vertically.

[`CanvasRenderingContext2D.translate()`](canvasrenderingcontext2d/translate)  
Adds a translation transformation by moving the canvas and its origin x horzontally and y vertically on the grid.

[`CanvasRenderingContext2D.transform()`](canvasrenderingcontext2d/transform)  
Multiplies the current transformation matrix with the matrix described by its arguments.

[`CanvasRenderingContext2D.setTransform()`](canvasrenderingcontext2d/settransform)  
Resets the current transform to the identity matrix, and then invokes the `transform()` method with the same arguments.

[`CanvasRenderingContext2D.resetTransform()`](canvasrenderingcontext2d/resettransform) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Resets the current transform by the identity matrix.

### Compositing

[`CanvasRenderingContext2D.globalAlpha`](canvasrenderingcontext2d/globalalpha)  
Alpha value that is applied to shapes and images before they are composited onto the canvas. Default `1.0` (opaque).

[`CanvasRenderingContext2D.globalCompositeOperation`](canvasrenderingcontext2d/globalcompositeoperation)  
With `globalAlpha` applied this sets how shapes and images are drawn onto the existing bitmap.

### Drawing images

[`CanvasRenderingContext2D.drawImage()`](canvasrenderingcontext2d/drawimage)  
Draws the specified image. This method is available in multiple formats, providing a great deal of flexibility in its use.

### Pixel manipulation

See also the [`ImageData`](imagedata) object.

[`CanvasRenderingContext2D.createImageData()`](canvasrenderingcontext2d/createimagedata)  
Creates a new, blank [`ImageData`](imagedata) object with the specified dimensions. All of the pixels in the new object are transparent black.

[`CanvasRenderingContext2D.getImageData()`](canvasrenderingcontext2d/getimagedata)  
Returns an [`ImageData`](imagedata) object representing the underlying pixel data for the area of the canvas denoted by the rectangle which starts at _(sx, sy)_ and has an _sw_ width and _sh_ height.

[`CanvasRenderingContext2D.putImageData()`](canvasrenderingcontext2d/putimagedata)  
Paints data from the given [`ImageData`](imagedata) object onto the bitmap. If a dirty rectangle is provided, only the pixels from that rectangle are painted.

### Image smoothing

[`CanvasRenderingContext2D.imageSmoothingEnabled`](canvasrenderingcontext2d/imagesmoothingenabled) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Image smoothing mode; if disabled, images will not be smoothed if scaled.

[`CanvasRenderingContext2D.imageSmoothingQuality`](canvasrenderingcontext2d/imagesmoothingquality) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Allows you to set the quality of image smoothing.

### The canvas state

The `CanvasRenderingContext2D` rendering context contains a variety of drawing style states (attributes for line styles, fill styles, shadow styles, text styles). The following methods help you to work with that state:

[`CanvasRenderingContext2D.save()`](canvasrenderingcontext2d/save)  
Saves the current drawing style state using a stack so you can revert any change you make to it using `restore()`.

[`CanvasRenderingContext2D.restore()`](canvasrenderingcontext2d/restore)  
Restores the drawing style state to the last element on the 'state stack' saved by `save()`.

[`CanvasRenderingContext2D.canvas`](canvasrenderingcontext2d/canvas)  
A read-only back-reference to the [`HTMLCanvasElement`](htmlcanvaselement). Might be [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) if it is not associated with a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element.

[`CanvasRenderingContext2D.getContextAttributes()`](canvasrenderingcontext2d/getcontextattributes)  
Returns an object containing the actual context attributes. Context attributes can be requested with [`HTMLCanvasElement.getContext()`](htmlcanvaselement/getcontext).

### Hit regions

[`CanvasRenderingContext2D.addHitRegion()`](canvasrenderingcontext2d/addhitregion) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Adds a hit region to the canvas.

[`CanvasRenderingContext2D.removeHitRegion()`](canvasrenderingcontext2d/removehitregion) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Removes the hit region with the specified `id` from the canvas.

[`CanvasRenderingContext2D.clearHitRegions()`](canvasrenderingcontext2d/clearhitregions) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Removes all hit regions from the canvas.

### Filters

<span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> [`CanvasRenderingContext2D.filter`](canvasrenderingcontext2d/filter)  
Applies a CSS or SVG filter to the canvas, e.g., to change its brightness or bluriness.

## Non-standard APIs

### Blink and WebKit

Most of these APIs are [deprecated and were removed shortly after Chrome 36](https://code.google.com/p/chromium/issues/detail?id=363198).

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.clearShadow()`  
Removes all shadow settings like [`CanvasRenderingContext2D.shadowColor`](canvasrenderingcontext2d/shadowcolor) and [`CanvasRenderingContext2D.shadowBlur`](canvasrenderingcontext2d/shadowblur).

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.drawImageFromRect()`  
This is redundant with an equivalent overload of `drawImage`.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.setAlpha()`  
Use [`CanvasRenderingContext2D.globalAlpha`](canvasrenderingcontext2d/globalalpha) instead.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.setCompositeOperation()`  
Use [`CanvasRenderingContext2D.globalCompositeOperation`](canvasrenderingcontext2d/globalcompositeoperation) instead.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.setLineWidth()`  
Use [`CanvasRenderingContext2D.lineWidth`](canvasrenderingcontext2d/linewidth) instead.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.setLineJoin()`  
Use [`CanvasRenderingContext2D.lineJoin`](canvasrenderingcontext2d/linejoin) instead.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.setLineCap()`  
Use [`CanvasRenderingContext2D.lineCap`](canvasrenderingcontext2d/linecap) instead.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.setMiterLimit()`  
Use [`CanvasRenderingContext2D.miterLimit`](canvasrenderingcontext2d/miterlimit) instead.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.setStrokeColor()`  
Use [`CanvasRenderingContext2D.strokeStyle`](canvasrenderingcontext2d/strokestyle) instead.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.setFillColor()`  
Use [`CanvasRenderingContext2D.fillStyle`](canvasrenderingcontext2d/fillstyle) instead.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.setShadow()`  
Use [`CanvasRenderingContext2D.shadowColor`](canvasrenderingcontext2d/shadowcolor) and [`CanvasRenderingContext2D.shadowBlur`](canvasrenderingcontext2d/shadowblur) instead.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.webkitLineDash`  
Use [`CanvasRenderingContext2D.getLineDash()`](canvasrenderingcontext2d/getlinedash) and [`CanvasRenderingContext2D.setLineDash()`](canvasrenderingcontext2d/setlinedash) instead.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.webkitLineDashOffset`  
Use [`CanvasRenderingContext2D.lineDashOffset`](canvasrenderingcontext2d/linedashoffset) instead.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.webkitImageSmoothingEnabled`  
Use [`CanvasRenderingContext2D.imageSmoothingEnabled`](canvasrenderingcontext2d/imagesmoothingenabled) instead.

### Blink only

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> `CanvasRenderingContext2D.isContextLost()`  
Inspired by the same `WebGLRenderingContext` method it returns `true` if the Canvas context has been lost, or `false` if not.

### WebKit only

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.webkitBackingStorePixelRatio`  
The backing store size in relation to the canvas element. See [High DPI Canvas](https://www.html5rocks.com/en/tutorials/canvas/hidpi/).

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.webkitGetImageDataHD`  
Intended for HD backing stores, but removed from canvas specifications.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.webkitPutImageDataHD`  
Intended for HD backing stores, but removed from canvas specifications.

### Gecko only

#### Prefixed APIs

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> `CanvasRenderingContext2D.mozCurrentTransform`  
Sets or gets the current transformation matrix, see [`CanvasRenderingContext2D.currentTransform`](canvasrenderingcontext2d/currenttransform).

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> `CanvasRenderingContext2D.mozCurrentTransformInverse`  
Sets or gets the current inversed transformation matrix.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> `CanvasRenderingContext2D.mozImageSmoothingEnabled`  
See [`CanvasRenderingContext2D.imageSmoothingEnabled`](canvasrenderingcontext2d/imagesmoothingenabled).

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.mozTextStyle`  
Introduced in Gecko 1.9, deprecated in favor of the [`CanvasRenderingContext2D.font`](canvasrenderingcontext2d/font) property.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.mozDrawText()`  
This method was introduced in Gecko 1.9 and is removed starting with Gecko 7.0. Use [`CanvasRenderingContext2D.strokeText()`](canvasrenderingcontext2d/stroketext) or [`CanvasRenderingContext2D.fillText()`](canvasrenderingcontext2d/filltext) instead.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.mozMeasureText()`  
This method was introduced in Gecko 1.9 and is unimplemented starting with Gecko 7.0. Use [`CanvasRenderingContext2D.measureText()`](canvasrenderingcontext2d/measuretext) instead.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.mozPathText()`  
This method was introduced in Gecko 1.9 and is removed starting with Gecko 7.0.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> `CanvasRenderingContext2D.mozTextAlongPath()`  
This method was introduced in Gecko 1.9 and is removed starting with Gecko 7.0.

#### Internal APIs (chrome-context only)

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> [`CanvasRenderingContext2D.drawWindow()`](canvasrenderingcontext2d/drawwindow)  
Renders a region of a window into the `canvas`. The contents of the window's viewport are rendered, ignoring viewport clipping and scrolling.

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> `CanvasRenderingContext2D.demote()`  
This causes a context that is currently using a hardware-accelerated backend to fallback to a software one. All state should be preserved.

### Internet Explorer

<span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> `CanvasRenderingContext2D.msFillRule`  
The [fill rule](https://cairographics.org/manual/cairo-cairo-t.html#cairo-fill-rule-t) to use. This must be one of `evenodd` or `nonzero` (default).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#2dcontext">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`CanvasRenderingContext2D`

1

12

1.5

9

9

2

1

18

4

10.1

1

1.0

`arc`

1

12

1.5

9

11.6

3

1

18

4

12

1

1.0

`arcTo`

1

12

1.5

9

11.6

2

1

18

4

12

1

1.0

`beginPath`

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

`bezierCurveTo`

1

12

1.5

9

11.6

2

1

18

4

12

1

1.0

`canvas`

1

12

1.5

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`clearRect`

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

`clip`

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

`closePath`

1

12

1.5

9

11.6

2

1

18

4

12

1

1.0

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

`createPattern`

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

`createRadialGradient`

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

`currentTransform`

32-68

≤18-79

No

See [bug 928150](https://bugzil.la/928150). Firefox also supports the experimental and prefixed properties mozCurrentTransform and mozCurrentTransformInverse which set or get the current (inverse) transformation matrix.

No

19-55

No

See [webkitbug(174278)](https://webkit.org/b/174278).

No

32-68

No

19-48

No

No

`direction`

77

39

79

No

No

64

26

9

77

77

No

55

9

12.0

`drawFocusIfNeeded`

37

14

32

28

No

24

8

37

37

32

28

24

8

3.0

`drawImage`

1

12

1.5

9

9

2

1

18

4

10.1

1

1.0

`drawWidgetAsOnScreen`

No

No

41

No

No

No

No

No

41

No

No

No

`drawWindow`

No

No

1.5

No

No

No

No

No

4

No

No

No

`ellipse`

31

13

48

No

18

9

4.4.3

31

48

18

9

2.0

`fill`

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

`fillRect`

1

12

1.5

9

9

2

1

18

4

10.1

1

1.0

`fillStyle`

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

`fillText`

1

12

3.5

9

≤12.1

4

1

18

4

≤12.1

3.2

1.0

`filter`

52

79

49

No

39

No

52

52

49

41

No

6.0

`font`

1

12

3.5

9

≤12.1

4

1

18

4

≤12.1

3.2

1.0

`getContextAttributes`

73

32-60

79

No

No

60

19-47

No

73

4.4.3-60

73

32-60

No

52

19-44

No

11.0

2.0-8.0

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

`getLineDash`

23

12

27

11

15

6.1

≤37

25

27

14

7

1.5

`getTransform`

68

79

70

No

55

11

68

68

No

48

11

10.0

`globalAlpha`

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

`globalCompositeOperation`

1

12

1.5

9

9

2

1

18

4

10.1

1

1.0

`imageSmoothingEnabled`

30

21-30

15

51

Yes-51

Yes

17

15-17

9.1

4.4

30

25-30

51

Yes-51

18

14-18

9.3

2.0

1.5-2.0

`imageSmoothingQuality`

54

79

No

No

41

9.1

54

54

No

41

9.3

6.0

`isPointInPath`

1

12

2

9

≤12.1

3.1

1

18

4

≤12.1

2

1.0

`isPointInStroke`

26

79

20

19-20

No

15

6.1

≤37

26

20

19-20

14

7

1.5

`lineCap`

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

`lineDashOffset`

23

12

27

7

11

15

6.1

≤37

25

27

7

14

7

1.5

`lineJoin`

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

`lineTo`

1

12

1.5

9

11.6

2

1

18

4

12

1

1.0

`lineWidth`

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

`measureText`

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

`miterLimit`

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

`moveTo`

1

12

1.5

9

11.6

2

1

18

4

12

1

1.0

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

`quadraticCurveTo`

1

12

1.5

9

11.6

3

1

18

4

12

1

1.0

`rect`

1

12

1.5

9

11.6

2

1

18

4

12

1

1.0

`resetTransform`

31

79

36

No

18

10.1

4.4

31

36

18

10.3

2.0

`restore`

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

`rotate`

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

`save`

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

`scale`

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

`scrollPathIntoView`

36

≤79

No

No

23

No

No

36

No

No

No

No

`setLineDash`

23

12

27

11

15

6.1

≤37

25

27

14

7

1.5

`setTransform`

1

12

3

9

≤12.1

4

1

18

4

≤12.1

3.2

1.0

`shadowBlur`

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

`shadowColor`

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

`shadowOffsetX`

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

`shadowOffsetY`

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

`stroke`

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

`strokeRect`

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

`strokeStyle`

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

`strokeText`

1

12

3.5

9

≤12.1

4

1

18

Yes

≤12.1

3.2

1.0

`textAlign`

1

12

3.5

9

≤12.1

4

1

18

4

≤12.1

3.2

1.0

`textBaseline`

1

12

3.5

9

≤12.1

4

1

18

4

≤12.1

3.2

1.0

`transform`

1

12

3

9

≤12.1

3.1

1

18

4

≤12.1

2

1.0

`translate`

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

## See also

- [`HTMLCanvasElement`](htmlcanvaselement)
- [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D</a>
