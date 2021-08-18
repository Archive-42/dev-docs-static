# Canvas API

The **Canvas API** provides a means for drawing graphics via [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) and the [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element. Among other things, it can be used for animation, game graphics, data visualization, photo manipulation, and real-time video processing.

The Canvas API largely focuses on 2D graphics. The [WebGL API](webgl_api), which also uses the `<canvas>` element, draws hardware-accelerated 2D and 3D graphics.

## Basic example

This simple example draws a green rectangle onto a canvas.

### HTML

    <canvas id="canvas"></canvas>

### JavaScript

The [`Document.getElementById()`](document/getelementbyid) method gets a reference to the HTML `<canvas>` element. Next, the [`HTMLCanvasElement.getContext()`](htmlcanvaselement/getcontext) method gets that element's context—the thing onto which the drawing will be rendered.

The actual drawing is done using the [`CanvasRenderingContext2D`](canvasrenderingcontext2d) interface. The [`fillStyle`](canvasrenderingcontext2d/fillstyle) property makes the rectangle green. The [`fillRect()`](canvasrenderingcontext2d/fillrect) method places its top-left corner at (10, 10), and gives it a size of 150 units wide by 100 tall.

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.fillStyle = 'green';
    ctx.fillRect(10, 10, 150, 100);

### Result

## Reference

- [`HTMLCanvasElement`](htmlcanvaselement)
- [`CanvasRenderingContext2D`](canvasrenderingcontext2d)
- [`CanvasGradient`](canvasgradient)
- [`CanvasImageSource`](canvasimagesource)
- [`CanvasPattern`](canvaspattern)
- [`ImageBitmap`](imagebitmap)
- [`ImageData`](imagedata)
- [`RenderingContext`](renderingcontext)
- [`TextMetrics`](textmetrics)
- [`OffscreenCanvas`](offscreencanvas) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`Path2D`](path2d) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`ImageBitmapRenderingContext`](imagebitmaprenderingcontext) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

**Note:** The interfaces related to the `WebGLRenderingContext` are referenced under [WebGL](webgl_api).

[`OffscreenCanvas`](offscreencanvas) is also available in web workers.

[`CanvasCaptureMediaStreamTrack`](canvascapturemediastreamtrack) is a related interface.

## Guides and tutorials

[Canvas tutorial](canvas_api/tutorial)  
A comprehensive tutorial covering both the basic usage of the Canvas API and its advanced features.

[HTML5 Canvas Deep Dive](https://joshondesign.com/p/books/canvasdeepdive/title.html)  
A hands-on, book-length introduction to the Canvas API and WebGL.

[Canvas Handbook](https://bucephalus.org/text/CanvasHandbook/CanvasHandbook.html)  
A handy reference for the Canvas API.

[Demo: A basic ray-caster](canvas_api/a_basic_ray-caster)  
A demo of ray-tracing animation using canvas.

[Manipulating video using canvas](canvas_api/manipulating_video_using_canvas)  
Combining [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) and [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) to manipulate video data in real time.

## Libraries

The Canvas API is extremely powerful, but not always simple to use. The libraries listed below can make the creation of canvas-based projects faster and easier.

- [EaselJS](https://www.createjs.com/easeljs) is an open-source canvas library that makes creating games, generative art, and other highly graphical experiences easy.
- [Fabric.js](http://fabricjs.com) is an open-source canvas library with SVG parsing capabilities.
- [heatmap.js](https://www.patrick-wied.at/static/heatmapjs/) is an open-source library for creating canvas-based data heat maps.
- [JavaScript InfoVis Toolkit](https://thejit.org/) creates interactive data visualizations.
- [Konva.js](https://konvajs.github.io/) is a 2D canvas library for desktop and mobile applications.
- [p5.js](https://p5js.org/) has a full set of canvas drawing functionality for artists, designers, educators, and beginners.
- [Paper.js](http://paperjs.org/) is an open-source vector graphics scripting framework that runs on top of the HTML5 Canvas.
- [Phaser](https://phaser.io/) is a fast, free and fun open source framework for Canvas and WebGL powered browser games.
- [Pts.js](https://ptsjs.org) is a library for creative coding and visualization in canvas and SVG.
- [Rekapi](https://github.com/jeremyckahn/rekapi) is an animation key-framing API for Canvas.
- [Scrawl-canvas](https://scrawl.rikweb.org.uk/) is an open-source JavaScript library for creating and manipulating 2D canvas elements.
- The [ZIM](https://zimjs.com) framework provides conveniences, components, and controls for coding creativity on the canvas — includes accessibility and hundreds of colorful tutorials.

**Note:** See the [WebGL API](webgl_api) for 2D and 3D libraries that use WebGL.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#2dcontext">HTML Living Standard<br />
<span class="small">The definition of 'the 2D rendering context' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

## Browser compatibility

## See also

- [WebGL](webgl_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API</a>
