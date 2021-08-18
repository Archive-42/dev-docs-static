# Hit regions and accessibility

- <a href="pixel_manipulation_with_canvas" class="button minimal">« Previous</a>
- <a href="optimizing_canvas" class="button minimal">Next »</a>

The [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element on its own is just a bitmap and does not provide information about any drawn objects. Canvas content is not exposed to accessibility tools like semantic HTML is. In general, you should avoid using canvas in an accessible website or app. The following guidelines can help to make it more accessible.

## Fallback content

The content inside the `<canvas> ... </canvas>` tags can be used as a fallback for browsers which don't support canvas rendering. It's also very useful for assistive technology users (like screen readers) which can read and interpret the sub DOM in it. A good example at [html5accessibility.com](https://www.html5accessibility.com/tests/canvas.html) demonstrates how this can be done:

    <canvas>
      <h2>Shapes</h2>
      <p>A rectangle with a black border.
       In the background is a pink circle.
       Partially overlaying the <a href="https://en.wikipedia.org/wiki/Circle" onfocus="drawCircle();" onblur="drawPicture();">circle</a>.
       Partially overlaying the circle is a green
       <a href="https://en.wikipedia.org/wiki/Square" onfocus="drawSquare();" onblur="drawPicture();">square</a>
       and a purple <a href="https://en.wikipedia.org/wiki/Triangle" onfocus="drawTriangle();" onblur="drawPicture();">triangle</a>,
       both of which are semi-opaque, so the full circle can be seen underneath.</p>
    </canvas>

See the [video how NVDA reads this example by Steve Faulkner](https://www.youtube.com/watch?v=ABeIFlqYiMQ).

## ARIA rules

Accessible Rich Internet Applications **([ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA))** defines ways to make Web content and Web applications more accessible to people with disabilities. You can use ARIA attributes to describe the behavior and purpose of the canvas element. See [ARIA](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA) and [ARIA techniques](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/ARIA_Techniques) for more information.

    <canvas id="button" tabindex="0" role="button" aria-pressed="false" aria-label="Start game"></canvas>

## Hit regions

Whether the mouse coordinates are within a particular area on the canvas, is a common problem to solve. The hit region API allows you to define an area of your canvas and provides another possibility to expose interactive content on a canvas to accessibility tools. It allows you to make hit detection easier and lets you route events to DOM elements. The API has the following three methods (which are still experimental in current web browsers; check the browser compatibility tables).

[`CanvasRenderingContext2D.addHitRegion()`](../../canvasrenderingcontext2d/addhitregion) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Adds a hit region to the canvas.

[`CanvasRenderingContext2D.removeHitRegion()`](../../canvasrenderingcontext2d/removehitregion) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Removes the hit region with the specified `id` from the canvas.

[`CanvasRenderingContext2D.clearHitRegions()`](../../canvasrenderingcontext2d/clearhitregions) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Removes all hit regions from the canvas.

You can add a hit region to your path and check for the [`MouseEvent.region`](../../mouseevent/region) property to test if your mouse is hitting your region, for example.

    <canvas id="canvas"></canvas>
    <script>
    var canvas = document.getElementById('canvas');
    var ctx = canvas.getContext('2d');

    ctx.beginPath();
    ctx.arc(70, 80, 10, 0, 2 * Math.PI, false);
    ctx.fill();
    ctx.addHitRegion({id: 'circle'});

    canvas.addEventListener('mousemove', function(event) {
      if (event.region) {
        alert('hit region: ' + event.region);
      }
    });
    </script>

The `addHitRegion()` method also takes a `control` option to route events to an element (that is a descendant of the canvas):

    ctx.addHitRegion({control: element});

This can be useful for routing to [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) elements, for example. See also this [codepen demo](https://codepen.io/peterj35/pen/PEdLKx).

## Focus rings

When working with the keyboard, focus rings are a handy indicator to help navigating on a page. To draw focus rings on a canvas drawing, the `drawFocusIfNeeded` property can be used.

[`CanvasRenderingContext2D.drawFocusIfNeeded()`](../../canvasrenderingcontext2d/drawfocusifneeded) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
If a given element is focused, this method draws a focus ring around the current path.

Additionally, the `scrollPathIntoView()` method can be used to make an element visible on the screen if focused, for example.

[`CanvasRenderingContext2D.scrollPathIntoView()`](../../canvasrenderingcontext2d/scrollpathintoview) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Scrolls the current path or a given path into the view.

## See also

- [Canvas accessibility use cases](https://www.w3.org/WAI/PF/HTML/wiki/Canvas_Accessibility_Use_Cases)
- [Canvas element accessibility issues](https://www.w3.org/html/wg/wiki/AddedElementCanvas)
- [HTML5 Canvas Accessibility in Firefox 13 – by Steve Faulkner](http://www.paciellogroup.com/blog/2012/06/html5-canvas-accessibility-in-firefox-13/)
- [Best practices for interactive canvas elements](https://html.spec.whatwg.org/multipage/scripting.html#best-practices)

<!-- -->

- <a href="pixel_manipulation_with_canvas" class="button minimal">« Previous</a>
- <a href="optimizing_canvas" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Hit_regions_and_accessibility" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Hit_regions_and_accessibility</a>
