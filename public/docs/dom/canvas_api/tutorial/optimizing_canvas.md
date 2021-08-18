# Optimizing canvas

- <a href="hit_regions_and_accessibility" class="button minimal">« Previous</a>
- <a href="finale" class="button minimal">Next »</a>

The [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element is one of the most widely used tools for rendering 2D graphics on the web. However, when websites and apps push the Canvas API to its limits, performance begins to suffer. This article provides suggestions for optimizing your use of the canvas element to ensure that your graphics perform well.

## Performance tips

The following is a collection of tips to improve canvas performance.

### Pre-render similar primitives or repeating objects on an offscreen canvas

If you find yourself repeating some of the same drawing operations on each animation frame, consider offloading them to an offscreen canvas. You can then render the offscreen image to your primary canvas as often as needed, without unnecessarily repeating the steps needed to generate it in the first place.

    myCanvas.offscreenCanvas = document.createElement('canvas');
    myCanvas.offscreenCanvas.width = myCanvas.width;
    myCanvas.offscreenCanvas.height = myCanvas.height;

    myCanvas.getContext('2d').drawImage(myCanvas.offScreenCanvas, 0, 0);

### Avoid floating-point coordinates and use integers instead

Sub-pixel rendering occurs when you render objects on a canvas without whole values.

    ctx.drawImage(myImage, 0.3, 0.5);

This forces the browser to do extra calculations to create the anti-aliasing effect. To avoid this, make sure to round all co-ordinates used in calls to [`drawImage()`](../../canvasrenderingcontext2d/drawimage) using [`Math.floor()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/floor), for example.

### Don’t scale images in `drawImage`

Cache various sizes of your images on an offscreen canvas when loading as opposed to constantly scaling them in [`drawImage()`](../../canvasrenderingcontext2d/drawimage).

### Use multiple layered canvases for complex scenes

In your application, you may find that some objects need to move or change frequently, while others remain relatively static. A possible optimization in this situation is to layer your items using multiple `<canvas>` elements.

For example, let's say you have a game with a UI on top, the gameplay action in the middle, and a static background on the bottom. In this case, you could split your game into three `<canvas>` layers. The UI would change only upon user input, the gameplay layer would change with every new frame, and the background would remain generally unchanged.

    <div id="stage">
      <canvas id="ui-layer" width="480" height="320"></canvas>
      <canvas id="game-layer" width="480" height="320"></canvas>
      <canvas id="background-layer" width="480" height="320"></canvas>
    </div>

    <style>
      #stage {
        width: 480px;
        height: 320px;
        position: relative;
        border: 2px solid black;
      }

      canvas { position: absolute; }
      #ui-layer { z-index: 3; }
      #game-layer { z-index: 2; }
      #background-layer { z-index: 1; }
    </style>

### Use plain CSS for large background images

If you have a static background image, you can draw it onto a plain [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) element using the CSS [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) property and position it under the canvas. This will negate the need to render the background to the canvas on every tick.

### Scaling canvas using CSS transforms

[CSS transforms](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transforms/Using_CSS_transforms) are faster since they use the GPU. The best case is to not scale the canvas, or have a smaller canvas and scale up rather than a bigger canvas and scale down.

    var scaleX = window.innerWidth / canvas.width;
    var scaleY = window.innerHeight / canvas.height;

    var scaleToFit = Math.min(scaleX, scaleY);
    var scaleToCover = Math.max(scaleX, scaleY);

    stage.style.transformOrigin = '0 0'; //scale from top left
    stage.style.transform = 'scale(' + scaleToFit + ')';

### Turn off transparency

If your application uses canvas and doesn’t need a transparent backdrop, set the `alpha` option to `false` when creating a drawing context with [`HTMLCanvasElement.getContext()`](../../htmlcanvaselement/getcontext). This information can be used internally by the browser to optimize rendering.

    var ctx = canvas.getContext('2d', { alpha: false });

### More tips

- Batch canvas calls together. For example, draw a polyline instead of multiple separate lines.
- Avoid unnecessary canvas state changes.
- Render screen differences only, not the whole new state.
- Avoid the [`shadowBlur`](../../canvasrenderingcontext2d/shadowblur) property whenever possible.
- Avoid [text rendering](drawing_text) whenever possible.
- Try different ways to clear the canvas ([`clearRect()`](../../canvasrenderingcontext2d/clearrect) vs. [`fillRect()`](../../canvasrenderingcontext2d/fillrect) vs. resizing the canvas).
- With animations, use [`window.requestAnimationFrame()`](../../window/requestanimationframe) instead of [`window.setInterval()`](../../windoworworkerglobalscope/setinterval) .
- Be careful with heavy physics libraries.

## See also

- [Improving HTML5 Canvas Performance – HTML5 Rocks](https://www.html5rocks.com/en/tutorials/canvas/performance/#toc-ref)
- [Optimizing your JavaScript game for Firefox OS – Mozilla Hacks](https://hacks.mozilla.org/2013/05/optimizing-your-javascript-game-for-firefox-os/)

<!-- -->

- <a href="hit_regions_and_accessibility" class="button minimal">« Previous</a>
- <a href="finale" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Optimizing_canvas" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Optimizing_canvas</a>
