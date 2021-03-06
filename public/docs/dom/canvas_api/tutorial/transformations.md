# Transformations

- <a href="using_images" class="button minimal">« Previous</a>
- <a href="compositing" class="button minimal">Next »</a>

Earlier in this tutorial we've learned about the [canvas grid](drawing_shapes) and the **coordinate space**. Until now, we only used the default grid and changed the size of the overall canvas for our needs. With transformations there are more powerful ways to translate the origin to a different position, rotate the grid and even scale it.

## Saving and restoring state

Before we look at the transformation methods, let's look at two other methods which are indispensable once you start generating ever more complex drawings.

[`save()`](../../canvasrenderingcontext2d/save)  
Saves the entire state of the canvas.

[`restore()`](../../canvasrenderingcontext2d/restore)  
Restores the most recently saved canvas state.

Canvas states are stored on a stack. Every time the `save()` method is called, the current drawing state is pushed onto the stack. A drawing state consists of

- The transformations that have been applied (i.e. `translate`, `rotate` and `scale` – see below).
- The current values of the following attributes: [`strokeStyle`](../../canvasrenderingcontext2d/strokestyle), [`fillStyle`](../../canvasrenderingcontext2d/fillstyle), [`globalAlpha`](../../canvasrenderingcontext2d/globalalpha), [`lineWidth`](../../canvasrenderingcontext2d/linewidth), [`lineCap`](../../canvasrenderingcontext2d/linecap), [`lineJoin`](../../canvasrenderingcontext2d/linejoin), [`miterLimit`](../../canvasrenderingcontext2d/miterlimit), [`lineDashOffset`](../../canvasrenderingcontext2d/linedashoffset), [`shadowOffsetX`](../../canvasrenderingcontext2d/shadowoffsetx), [`shadowOffsetY`](../../canvasrenderingcontext2d/shadowoffsety), [`shadowBlur`](../../canvasrenderingcontext2d/shadowblur), [`shadowColor`](../../canvasrenderingcontext2d/shadowcolor), [`globalCompositeOperation`](../../canvasrenderingcontext2d/globalcompositeoperation), [`font`](../../canvasrenderingcontext2d/font), [`textAlign`](../../canvasrenderingcontext2d/textalign), [`textBaseline`](../../canvasrenderingcontext2d/textbaseline), [`direction`](../../canvasrenderingcontext2d/direction), [`imageSmoothingEnabled`](../../canvasrenderingcontext2d/imagesmoothingenabled).
- The current [clipping path](compositing#clipping_paths), which we'll see in the next section.

You can call the `save()` method as many times as you like. Each time the `restore()` method is called, the last saved state is popped off the stack and all saved settings are restored.

### A `save` and `restore` canvas state example

This example tries to illustrate how the stack of drawing states functions by drawing a set of consecutive rectangles.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');

      ctx.fillRect(0, 0, 150, 150);   // Draw a rectangle with default settings
      ctx.save();                  // Save the default state

      ctx.fillStyle = '#09F';      // Make changes to the settings
      ctx.fillRect(15, 15, 120, 120); // Draw a rectangle with new settings

      ctx.save();                  // Save the current state
      ctx.fillStyle = '#FFF';      // Make changes to the settings
      ctx.globalAlpha = 0.5;
      ctx.fillRect(30, 30, 90, 90);   // Draw a rectangle with new settings

      ctx.restore();               // Restore previous state
      ctx.fillRect(45, 45, 60, 60);   // Draw a rectangle with restored settings

      ctx.restore();               // Restore original state
      ctx.fillRect(60, 60, 30, 30);   // Draw a rectangle with restored settings
    }

The first step is to draw a large rectangle with the default settings. Next we save this state and make changes to the fill color. We then draw the second and smaller blue rectangle and save the state. Again we change some drawing settings and draw the third semi-transparent white rectangle.

So far this is pretty similar to what we've done in previous sections. However once we call the first `restore()` statement, the top drawing state is removed from the stack, and settings are restored. If we hadn't saved the state using `save()`, we would need to change the fill color and transparency manually in order to return to the previous state. This would be easy for two properties, but if we have more than that, our code would become very long, very fast.

When the second `restore()` statement is called, the original state (the one we set up before the first call to `save`) is restored and the last rectangle is once again drawn in black.

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAL4AAAC+BAMAAAB5WqiuAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAACFQTFRFfsz/AJj/AAAA////9/f3/v7++fn5zMzM+/v7/f394eHhgBpX7wAAAUlJREFUeNrt3LtKA0EYhuH1DtQ70FuI4qE1JCG9iL2obOspWksO1kJi7RJlrtJ/ujGFZHa/2QzyfkXKJ28VwrCzRSftCnx8/NR++fWk3ct36L+7qqvd0J0Ffqnm7QuqwHdd/VyL/n0Cv4+fl7+vGz4+Pj6+3t/bqb9dfHx8/Nz8K5vQ79k23V/ErEZ/E59++umnP5f+x2ub0PfczXr+1p8/+Nv4+Pj4+Bv2V05IIv2xTejf2uinn3766W/eP5rahL7nJvj4+Pj40f/PW/cXNqE/s9FPP/30Z95f63w7or+Wv9r//GET+p6b4+Pj42fqN3k+BD/Ofzi3CX3PXeDj4/87XzF8fPz2/Dv/IfQ9d4Sfly8e/vr+KIEfnP+cVHr+eBjeX07QH95fLj/l/Oky8A/cQMy//rqffvkmv1+/TPt+gEPen4CPn9z/AQmJbycPyfe5AAAAAElFTkSuQmCC" class="internal" /></td><td></td></tr></tbody></table>

## Translating

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAANwAAADcCAMAAAAshD+zAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAGlQTFRF9vb2/Pz8+fn5+vr69/f3/f39+Pj4/v7+////5eXl+/v7zMzMAAAA5jUApqamz8/P6urqurq6SUlJ+M/CYWFh29vbfHx88fHxMzMz7W5I8puB4ODg++3pk5OT8IZmFhYW9bWhrq6u61ouTLUuRwAAA8JJREFUeNrt3etyqjAUBWCKKEFAAiTc8fb+D3mirR174HiIBU32rDVDfiBN+WYnxDJ0cBjhOMABBxxwwAEHHAGcy2USWpxEcvcfON+RLS8de+OVvJXOOM6VgWN9AumO4njrEEjLR3GSU8BxOYpLSgI2r0xGcaFDIiFw6tKTVVlAFZeFTpgRxQUXmHWlm4hLC9UUKVGcUI0ginOqr40krhep6Mmuc6l1M24Czp4FLlAjKw21cPYscF4WBlUwAefdwjPVZNyzIbIq+h87/oNTU021RaqayFhUdDu1IvN0cF4qVCPSSw9G53qyotLDedXX5kXfnwYjd5fG9sUTj4smHjeyb3dfuTTrCz3cdYEzG/ddB+lVXAe38dLrjFsQpwbVHLjNrlCXCKFVOc+5TVvDcV9EVwvnLY2bbVgOAhxwwBmLC25JgmHG9sUTj4smHjeyD5UDDjjggAMOOOCAA446rk0YK9N34DbDzI47lKwQv8VtHuV9OF8U7NASxanS9RmjivNFlJLFsV3G6FauOpmDm/seyukwwz0UUytXnBjdYTnLNxTggAMOOOCAA25OXFfXdUcVV+csr4ninPoC7IzFucNMx+WNapr8JTj3URbB7VWzJ4pj58/tFU8Q3Z1gd3TdPF8cd9zn++PLcW6dd3W3OE7NuvxF69z9GXZ1c1x+WGou4sEvcXF8PUHPaeqn51xscq6nuD+7ZCuX101DDvd9Qencc0cTtzo2qnh7opVbqW1Ddli+5hsKcMABBxxwBHCrYczErR4FOOCAAw64mXGL/S/PL/ahcsABBxxwwAEHHBHcdphRnF+eSpYm78NtH+WXOMaESA5UcX5ZRTtGtXJ+fyjJ4k4HUVHFXSZcJsjOOcboDss3r3Mz4j6f9Znyiy9H2oTTzUvuoaBymHPAAQcccE/gPoYxE/fxKMABBxxwwAEHHHDAmYoz8jkUVA444IADbincehgzcetHAQ444IADDjjggAMOuDfgjLyHgsoBBxxwwAH3BM4fxkyc/yjAAQcccMABBxxwVuN2uol3y2cunK+b2H9zgAPOZlwU6eriOAYOwxK453EWBjjauHWvmvak0S9r1E91Rysq1xe+nyU6HTdKV+dG4v76y8JfZ2VaMK3U3fUtL+/MNBxjqahKvZ7z/bmzBMfETrNn//KCF0twRarb9fUNL8ABtyTOxgAHHHAm4JItBds2GcXJkgKulKM43lLAtXwU50puv41LdxTHHNmWVs+7bdnKH6D7D10uk9DiJJK77F84agEOOOCAAw444CzNHwesR0NavrQNAAAAAElFTkSuQmCC" class="internal" width="220" height="220" />The first of the transformation methods we'll look at is `translate()`. This method is used to move the canvas and its origin to a different point in the grid.

[`translate(x, y)`](../../canvasrenderingcontext2d/translate)  
Moves the canvas and its origin on the grid. `x` indicates the horizontal distance to move, and `y` indicates how far to move the grid vertically.

It's a good idea to save the canvas state before doing any transformations. In most cases, it is just easier to call the `restore` method than having to do a reverse translation to return to the original state. Also if you're translating inside a loop and don't save and restore the canvas state, you might end up missing part of your drawing, because it was drawn outside the canvas edge.

### A `translate` example

This example demonstrates some of the benefits of translating the canvas origin. Without the `translate()` method, all of the rectangles would be drawn at the same position (0,0). The `translate()` method also gives us the freedom to place the rectangle anywhere on the canvas without having to manually adjust coordinates in the `fillRect()` function. This makes it a little easier to understand and use.

In the `draw()` function, we call the `fillRect()` function nine times using two `for` loops. In each loop, the canvas is translated, the rectangle is drawn, and the canvas is returned back to its original state. Note how the call to `fillRect()` uses the same coordinates each time, relying on `translate()` to adjust the drawing position.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');
      for (var i = 0; i < 3; i++) {
        for (var j = 0; j < 3; j++) {
          ctx.save();
          ctx.fillStyle = 'rgb(' + (51 * i) + ', ' + (255 - 51 * i) + ', 255)';
          ctx.translate(10 + j * 50, 10 + i * 50);
          ctx.fillRect(0, 0, 25, 25);
          ctx.restore();
        }
      }
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAJEAAACUAgMAAADueyMDAAAAGXRFWHRTb2Z0d2FyZQBnbm9tZS1zY3JlZW5zaG907wO/PgAAAAxQTFRFM8z/Zpn/AP//////hfVAagAAAGhJREFUWMPt1LsRgDAMg2FvwHSp2S8NK2SJLMEMvM4KpKbD4X5V8umrbeeLFEN9qdbsWXQf6rmNfUChULEU/wuFGk0V80y6N3V7xntAoVCxFP8LhRpN1eSZde/qqY19QKFQsRT/6wfqAsunl17nZjqRAAAAAElFTkSuQmCC" class="internal" /></td><td></td></tr></tbody></table>

## Rotating

<img src="data:image/png;base64,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" class="internal" width="220" height="220" />The second transformation method is `rotate()`. We use it to rotate the canvas around the current origin.

[`rotate(angle)`](../../canvasrenderingcontext2d/rotate)  
Rotates the canvas clockwise around the current origin by the `angle` number of radians.

The rotation center point is always the canvas origin. To change the center point, we will need to move the canvas by using the `translate()` method.

### A `rotate` example

In this example, we'll use the `rotate()` method to first rotate a rectangle from the canvas origin and then from the center of the rectangle itself with the help of `translate()`.

**Reminder**: Angles are in radians, not degrees. To convert, we are using: `radians = (Math.PI/180)*degrees`.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');

      // left rectangles, rotate from canvas origin
      ctx.save();
      // blue rect
      ctx.fillStyle = '#0095DD';
      ctx.fillRect(30, 30, 100, 100);
      ctx.rotate((Math.PI / 180) * 25);
      // grey rect
      ctx.fillStyle = '#4D4E53';
      ctx.fillRect(30, 30, 100, 100);
      ctx.restore();

      // right rectangles, rotate from rectangle center
      // draw blue rect
      ctx.fillStyle = '#0095DD';
      ctx.fillRect(150, 30, 100, 100);

      ctx.translate(200, 80); // translate to rectangle center
                              // x = x + 0.5 * width
                              // y = y + 0.5 * height
      ctx.rotate((Math.PI / 180) * 25); // rotate
      ctx.translate(-200, -80); // translate back

      // draw grey rect
      ctx.fillStyle = '#4D4E53';
      ctx.fillRect(150, 30, 100, 100);
    }

To rotate the rectangle around its own center, we translate the canvas to the center of the rectangle, then rotate the canvas, then translate the canvas back to 0,0, and then draw the rectangle.

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

## Scaling

The next transformation method is scaling. We use it to increase or decrease the units in our canvas grid. This can be used to draw scaled down or enlarged shapes and bitmaps.

[`scale(x, y)`](../../canvasrenderingcontext2d/scale)  
Scales the canvas units by x horizontally and by y vertically. Both parameters are real numbers. Values that are smaller than 1.0 reduce the unit size and values above 1.0 increase the unit size. Values of 1.0 leave the units the same size.

Using negative numbers you can do axis mirroring (for example using `translate(0,canvas.height); scale(1,-1);` you will have the well-known Cartesian coordinate system, with the origin in the bottom left corner).

By default, one unit on the canvas is exactly one pixel. If we apply, for instance, a scaling factor of 0.5, the resulting unit would become 0.5 pixels and so shapes would be drawn at half size. In a similar way setting the scaling factor to 2.0 would increase the unit size and one unit now becomes two pixels. This results in shapes being drawn twice as large.

### A `scale` example

In this last example, we'll draw shapes with different scaling factors.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');

      // draw a simple rectangle, but scale it.
      ctx.save();
      ctx.scale(10, 3);
      ctx.fillRect(1, 10, 10, 10);
      ctx.restore();

      // mirror horizontally
      ctx.scale(-1, 1);
      ctx.font = '48px serif';
      ctx.fillText('MDN', -135, 120);
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAJoAAAB0CAMAAABKb9vXAAAAGXRFWHRTb2Z0d2FyZQBnbm9tZS1zY3JlZW5zaG907wO/PgAAAH5QTFRFAAAAz8/PIyMjd3d3S0tL9PT0AwMD////GxsbDw8Pc3NzCQkJqamp/v7+VlZW6urqKSkpmpqaiIiI4eHh+/v7a2tr2NjYFBQUsrKyMjIyxcXFX19fkZGRSEhIvb29QkJCgYGBcHBwPDw8Hx8f8PDwZWVloKCge3t7pKSkzMzMS37KtwAAA61JREFUeNrt2W2XoiAUAGB6UTIzrdReLK3GaWb+/x9cuJiB4lFwZ3b2nOuXcUHzEeFyYQn9tQdBGtKQhjSk/Rsa+YEDaUhDGtKQhjSkIQ1pSEMa0pCGNKQhDWn/Aw3315CGNKQhDWlIQxrSkIY0pCENaT9HW0gL2Y16WTB/Vqybv7DbJMXU89V18IrXXJ7/cnf6hwdRfcO7Ne1M9LRwG2mX6CqN3PSyAxlKuy6Xy4yQN/ZneVKu+nLh5XnFp1RczqrGiop1wis9du7zkwmv3rCTBOr9UEs7ikp+w6q/r00ImbcuKqfwG16jOH8T7biqH8yvWyjXOML+oZPlom4xcBjoaMGa6GgbaMr5RCrqpHml5tn38bQN0dFE6TWg/TT22bftR5+qqhG0FDrUm6/Scmizh3ppB+0yJXun9WgYJYk7gubAGHRPnkIrYTgndBBtzlr4TNtP4mFlDO0dPtyWqrQbDExnIC1ekEXcuBY6cEZH0FYguwQqLfQ1n7ObxuNiI1Km8LvpCFrqwSBi4UGhbXlpu/900pw9marNllXx25YWxBAV3Zw2aEd9jO+k0SshcrAOdjCKvuxpokuRK23QwtdsNJBWeiSS4wzMEhdqTxOTXBE3aNXktzOg0Rkhh1ejib6a29N2e+hSYh6SW010NWpCY5jjq9mWvPhOrWmxmEly2qJBQImMaPwT5soAdw/2tA9lZpZp6/qlh9NYxy/qHIeXika0oonE4B5raPP6gcNpPFxUqVbpvUaRDS2EqWhf9/XRtLS+BbpqFecsaIHIUV+jauwHhbsgg3L20lRiQYM3I0uqpSUWwwB+e11n88851Zx24tHaPcZ6mggegSGN94OUDXxIjp+ZiDGthNs9OajKNIuQWyWPGaUPZf41pVUp94F20MwnqmfK7e7iSCRZljSRXKuJYnt6T4xpLB4lK3WtYEibwAx3jLtp0Nk8x5TGlnd+pK6wzGgi5fZS2k0T0/PGlFYlpvK61IyWaXuSmoDPIGo6prRqK0HK9Ixonn6lr9KchUjtDWlieMp7IEY0uLm1ImnQROBrftJ+GgQ1+bWNaX5Ke2ji/YctkeXZ9rMoinQM7UF7afQB7XaZmNGahyktowNo9DR0O+Yv0pod7XPGDpe4/I+8LnI+qk2s4zy78UrYxOIn0JQHdgLrnikvau9jnXixfEM/zZ/oFtrmW38zpajde8/NG/pprUjaTas3TN3vp4XX6zn4nTvgv4SF/2+ANKQhDWlIQxrSfvb4AwyojDM68HEpAAAAAElFTkSuQmCC" class="internal" /></td><td></td></tr></tbody></table>

## Transforms

Finally, the following transformation methods allow modifications directly to the transformation matrix.

[`transform(a, b, c, d, e, f)`](../../canvasrenderingcontext2d/transform)  
Multiplies the current transformation matrix with the matrix described by its arguments. The transformation matrix is described by: $\\begin{bmatrix}
a & c & e \\\\
b & d & f \\\\
0 & 0 & 1 \\\\
\\end{bmatrix}$  
If any of the arguments are `Infinity` the transformation matrix must be marked as infinite instead of the method throwing an exception.

The parameters of this function are:

`a (m11)`  
Horizontal scaling.

_`b (m12)`_  
Horizontal skewing.

`c (m21)`  
Vertical skewing.

`d (m22)`  
Vertical scaling.

`e (dx)`  
Horizontal moving.

`f (dy)`  
Vertical moving.

[`setTransform(a, b, c, d, e, f)`](../../canvasrenderingcontext2d/settransform)  
Resets the current transform to the identity matrix, and then invokes the `transform()` method with the same arguments. This basically undoes the current transformation, then sets the specified transform, all in one step.

[`resetTransform()`](../../canvasrenderingcontext2d/resettransform)  
Resets the current transform to the identity matrix. This is the same as calling: `ctx.setTransform(1, 0, 0, 1, 0, 0);`

### Example for `transform` and `setTransform`

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');

      var sin = Math.sin(Math.PI / 6);
      var cos = Math.cos(Math.PI / 6);
      ctx.translate(100, 100);
      var c = 0;
      for (var i = 0; i <= 12; i++) {
        c = Math.floor(255 / 12 * i);
        ctx.fillStyle = 'rgb(' + c + ', ' + c + ', ' + c + ')';
        ctx.fillRect(0, 0, 100, 10);
        ctx.transform(cos, sin, -sin, cos, 0, 0);
      }

      ctx.setTransform(-1, 0, 0, 1, 100, 100);
      ctx.fillStyle = 'rgba(255, 128, 255, 0.5)';
      ctx.fillRect(0, 50, 100, 100);
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

- <a href="using_images" class="button minimal">« Previous</a>
- <a href="compositing" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Transformations" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Transformations</a>
