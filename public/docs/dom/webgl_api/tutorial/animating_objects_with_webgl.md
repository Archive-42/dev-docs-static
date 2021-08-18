Animating objects with WebGL
============================

-   <a href="using_shaders_to_apply_color_in_webgl" class="button minimal">« Previous</a>
-   <a href="creating_3d_objects_using_webgl" class="button minimal">Next »</a>

In this example, we'll actually rotate our square plane.

This example uses the glMatrix library to perform its matrix and vertex math. You'll need to include it if you create your own project based on this code. Our sample loads a copy from a CDN in our HTML's [`<head>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head).

Making the square rotate
------------------------

Let's start by making the square rotate. The first thing we'll need is a variable in which to track the current rotation of the square:

    var squareRotation = 0.0;

Now we need to update the `drawScene()` function to apply the current rotation to the square when drawing it. After translating to the initial drawing position for the square, we apply the rotation like this:

      mat4.rotate(modelViewMatrix,  // destination matrix
                  modelViewMatrix,  // matrix to rotate
                  squareRotation,   // amount to rotate in radians
                  [0, 0, 1]);       // axis to rotate around

This rotates the modelViewMatrix by the current value of `squareRotation`, around the Z axis.

To actually animate, we need to add code that changes the value of `squareRotation` over time. We can do that by creating a new variable to track the time at which we last animated (let's call it `then`), then adding the following code to the end of the main function

      var then = 0;

      // Draw the scene repeatedly
      function render(now) {
        now *= 0.001;  // convert to seconds
        const deltaTime = now - then;
        then = now;

        drawScene(gl, programInfo, buffers, deltaTime);

        requestAnimationFrame(render);
      }
      requestAnimationFrame(render);

This code uses `requestAnimationFrame` to ask the browser to call the function "`render`" on each frame. `requestAnimationFrame` passes us the time in milliseconds since the page loaded. We convert that to seconds and then subtract from it the last time to compute `deltaTime` which is the number of second since the last frame was rendered. At the end of drawscene we add the code to update `squareRotation.`

    squareRotation += deltaTime;

This code uses the amount of time that's passed since the last time we updated the value of `squareRotation` to determine how far to rotate the square.

[View the complete code](https://github.com/mdn/webgl-examples/tree/gh-pages/tutorial/sample4) | [Open this demo on a new page](https://mdn.github.io/webgl-examples/tutorial/sample4/)

-   <a href="using_shaders_to_apply_color_in_webgl" class="button minimal">« Previous</a>
-   <a href="creating_3d_objects_using_webgl" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Animating_objects_with_WebGL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Animating_objects_with_WebGL</a>
