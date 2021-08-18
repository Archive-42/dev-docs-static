Scissor animation
=================

### Animation with scissoring

-   <a href="boilerplate_1" class="button minimal">« Previous</a>
-   <a href="raining_rectangles" class="button minimal">Next »</a>

A simple WebGL example in which we have some animation fun using scissoring and clearing operations.

In this example, we are animating squares using [`scissor()`](../../webglrenderingcontext/scissor) and [`clear()`](../../webglrenderingcontext/clear). We again establish an animation loop using timers. Note that this time it is the position of the square (the scissoring area) that is updated every frame (we set frame rate to roughly one every 17ms, or roughly 60fps – frames per second).

In contrast, the color of the square (set with [`clearColor`](../../webglrenderingcontext/clearcolor)) is only updated when a new square is created. This is a nice demonstration of [WebGL](https://developer.mozilla.org/en-US/docs/Glossary/WebGL) as a state machine. For each square, we set its color once, and then update only its position every frame. The clear color state of WebGL remains at the set value, until we change it again when a new square is created.

    "use strict"
    window.addEventListener("load", setupAnimation, false);
    // Variables to hold the WebGL context, and the color and
    // position of animated squares.
    var gl,
      color = getRandomColor(),
      position;

    function setupAnimation (evt) {
      window.removeEventListener(evt.type, setupAnimation, false);
      if (!(gl = getRenderingContext()))
        return;

      gl.enable(gl.SCISSOR_TEST);
      gl.clearColor(color[0], color[1], color[2], 1.0);
      // Unlike the browser window, vertical position in WebGL is
      // measured from bottom to top. In here we set the initial
      // position of the square to be at the top left corner of the
      // drawing buffer.
      position = [0, gl.drawingBufferHeight];

      var button = document.querySelector("button");
      var timer;
      function startAnimation(evt) {
        button.removeEventListener(evt.type, startAnimation, false);
        button.addEventListener("click", stopAnimation, false);
        document.querySelector("strong").textContent = "stop";
        timer = setInterval(drawAnimation, 17);
        drawAnimation();
      }
      function stopAnimation(evt) {
        button.removeEventListener(evt.type, stopAnimation, false);
        button.addEventListener("click", startAnimation, false);
        document.querySelector("strong").textContent = "start";
        clearInterval(timer);
      }
      stopAnimation({type: "click"});
    }

    // Variables to hold the size and velocity of the square.
    var size = [60, 60],
      velocity = 3.0;
    function drawAnimation () {
      gl.scissor(position[0], position[1], size[0] , size[1]);
      gl.clear(gl.COLOR_BUFFER_BIT);
      // Every frame the vertical position of the square is
      // decreased, to create the illusion of movement.
      position[1] -= velocity;
      // When the sqaure hits the bottom of the drawing buffer,
      // we override it with new square of different color and
      // velocity.
      if (position[1] < 0) {
        // Horizontal position chosen randomly, and vertical
        // position at the top of the drawing buffer.
        position = [
          Math.random()*(gl.drawingBufferWidth - size[0]),
          gl.drawingBufferHeight
        ];
        // Random velocity between 1.0 and 7.0
        velocity = 1.0 + 6.0*Math.random();
        color = getRandomColor();
        gl.clearColor(color[0], color[1], color[2], 1.0);
      }
    }

    function getRandomColor() {
      return [Math.random(), Math.random(), Math.random()];
    }

The source code of this example is also available on [GitHub](https://github.com/idofilin/webgl-by-example/tree/master/scissor-animation).

-   <a href="boilerplate_1" class="button minimal">« Previous</a>
-   <a href="raining_rectangles" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example/Scissor_animation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example/Scissor_animation</a>
