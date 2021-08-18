# Compositing and clipping

- <a href="transformations" class="button minimal">« Previous</a>
- <a href="basic_animations" class="button minimal">Next »</a>

In all of our [previous examples](transformations), shapes were always drawn one on top of the other. This is more than adequate for most situations, but it limits the order in which composite shapes are built. We can, however, change this behavior by setting the `globalCompositeOperation` property. In addition, the `clip` property allows us to hide unwanted parts of shapes.

## `globalCompositeOperation`

We can not only draw new shapes behind existing shapes but we can also use it to mask off certain areas, clear sections from the canvas (not limited to rectangles like the [`clearRect()`](../../canvasrenderingcontext2d/clearrect) method does) and more.

[`globalCompositeOperation = type`](../../canvasrenderingcontext2d/globalcompositeoperation)  
This sets the type of compositing operation to apply when drawing new shapes, where type is a string identifying which of the twelve compositing operations to use.

See [compositing examples](compositing/example) for the code of the following examples.

## Clipping paths

<img src="data:image/png;base64,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" class="internal" width="220" height="220" />A clipping path is like a normal canvas shape but it acts as a mask to hide unwanted parts of shapes. This is visualized in the image on the right. The red star shape is our clipping path. Everything that falls outside of this path won't get drawn on the canvas.

If we compare clipping paths to the `globalCompositeOperation` property we've seen above, we see two compositing modes that achieve more or less the same effect in `source-in` and `source-atop`. The most important differences between the two are that clipping paths are never actually drawn to the canvas and the clipping path is never affected by adding new shapes. This makes clipping paths ideal for drawing multiple shapes in a restricted area.

In the chapter about [drawing shapes](drawing_shapes) I only mentioned the `stroke()` and `fill()` methods, but there's a third method we can use with paths, called `clip()`.

[`clip()`](../../canvasrenderingcontext2d/clip)  
Turns the path currently being built into the current clipping path.

You use `clip()` instead of `closePath()` to close a path and turn it into a clipping path instead of stroking or filling the path.

By default the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element has a clipping path that's the exact same size as the canvas itself. In other words, no clipping occurs.

### A `clip` example

In this example, we'll use a circular clipping path to restrict the drawing of a set of random stars to a particular region.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');
      ctx.fillRect(0, 0, 150, 150);
      ctx.translate(75, 75);

      // Create a circular clipping path
      ctx.beginPath();
      ctx.arc(0, 0, 60, 0, Math.PI * 2, true);
      ctx.clip();

      // draw background
      var lingrad = ctx.createLinearGradient(0, -75, 0, 75);
      lingrad.addColorStop(0, '#232256');
      lingrad.addColorStop(1, '#143778');

      ctx.fillStyle = lingrad;
      ctx.fillRect(-75, -75, 150, 150);

      // draw stars
      for (var j = 1; j < 50; j++) {
        ctx.save();
        ctx.fillStyle = '#fff';
        ctx.translate(75 - Math.floor(Math.random() * 150),
                      75 - Math.floor(Math.random() * 150));
        drawStar(ctx, Math.floor(Math.random() * 4) + 2);
        ctx.restore();
      }

    }

    function drawStar(ctx, r) {
      ctx.save();
      ctx.beginPath();
      ctx.moveTo(r, 0);
      for (var i = 0; i < 9; i++) {
        ctx.rotate(Math.PI / 5);
        if (i % 2 === 0) {
          ctx.lineTo((r / 0.525731) * 0.200811, 0);
        } else {
          ctx.lineTo(r, 0);
        }
      }
      ctx.closePath();
      ctx.fill();
      ctx.restore();
    }

In the first few lines of code, we draw a black rectangle the size of the canvas as a backdrop, then translate the origin to the center. Next, we create the circular clipping path by drawing an arc and calling `clip()`. Clipping paths are also part of the canvas save state. If we wanted to keep the original clipping path we could have saved the canvas state before creating the new one.

Everything that's drawn after creating the clipping path will only appear inside that path. You can see this clearly in the linear gradient that's drawn next. After this a set of 50 randomly positioned and scaled stars is drawn, using the custom `drawStar()` function. Again the stars only appear inside the defined clipping path.

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

- <a href="transformations" class="button minimal">« Previous</a>
- <a href="basic_animations" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Compositing" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Compositing</a>
