# Advanced animations

- <a href="basic_animations" class="button minimal">« Previous</a>
- <a href="pixel_manipulation_with_canvas" class="button minimal">Next »</a>

In the last chapter we made some [basic animations](basic_animations) and got to know ways to get things moving. In this part we will have a closer look at the motion itself and are going to add some physics to make our animations more advanced.

## Drawing a ball

We are going to use a ball for our animation studies, so let's first draw that ball onto the canvas. The following code will set us up.

    <canvas id="canvas" width="600" height="300"></canvas>

As usual, we need a drawing context first. To draw the ball, we will create a `ball` object which contains properties and a `draw()` method to paint it on the canvas.

    var canvas = document.getElementById('canvas');
    var ctx = canvas.getContext('2d');

    var ball = {
      x: 100,
      y: 100,
      radius: 25,
      color: 'blue',
      draw: function() {
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2, true);
        ctx.closePath();
        ctx.fillStyle = this.color;
        ctx.fill();
      }
    };

    ball.draw();

Nothing special here, the ball is actually a simple circle and gets drawn with the help of the [`arc()`](../../canvasrenderingcontext2d/arc) method.

## Adding velocity

Now that we have a ball, we are ready to add a basic animation like we have learned in the [last chapter](basic_animations) of this tutorial. Again, [`window.requestAnimationFrame()`](../../window/requestanimationframe) helps us to control the animation. The ball gets moving by adding a velocity vector to the position. For each frame, we also [clear](../../canvasrenderingcontext2d/clearrect) the canvas to remove old circles from prior frames.

    var canvas = document.getElementById('canvas');
    var ctx = canvas.getContext('2d');
    var raf;

    var ball = {
      x: 100,
      y: 100,
      vx: 5,
      vy: 2,
      radius: 25,
      color: 'blue',
      draw: function() {
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2, true);
        ctx.closePath();
        ctx.fillStyle = this.color;
        ctx.fill();
      }
    };

    function draw() {
      ctx.clearRect(0,0, canvas.width, canvas.height);
      ball.draw();
      ball.x += ball.vx;
      ball.y += ball.vy;
      raf = window.requestAnimationFrame(draw);
    }

    canvas.addEventListener('mouseover', function(e) {
      raf = window.requestAnimationFrame(draw);
    });

    canvas.addEventListener('mouseout', function(e) {
      window.cancelAnimationFrame(raf);
    });

    ball.draw();

## Boundaries

Without any boundary collision testing our ball runs out of the canvas quickly. We need to check if the `x` and `y` position of the ball is out of the canvas dimensions and invert the direction of the velocity vectors. To do so, we add the following checks to the `draw` method:

    if (ball.y + ball.vy > canvas.height || ball.y + ball.vy < 0) {
      ball.vy = -ball.vy;
    }
    if (ball.x + ball.vx > canvas.width || ball.x + ball.vx < 0) {
      ball.vx = -ball.vx;
    }

### First demo

Let's see how it looks in action so far. Move your mouse into the canvas to start the animation.

## Acceleration

To make the motion more real, you can play with the velocity like this, for example:

    ball.vy *= .99;
    ball.vy += .25;

This slows down the vertical velocity each frame, so that the ball will just bounce on the floor in the end.

## Trailing effect

Until now we have made use of the [`clearRect`](../../canvasrenderingcontext2d/clearrect) method when clearing prior frames. If you replace this method with a semi-transparent [`fillRect`](../../canvasrenderingcontext2d/fillrect), you can easily create a trailing effect.

    ctx.fillStyle = 'rgba(255, 255, 255, 0.3)';
    ctx.fillRect(0, 0, canvas.width, canvas.height);

## Adding mouse control

To get some control over the ball, we can make it follow our mouse using the `mousemove` event, for example. The `click` event releases the ball and lets it bounce again.

    var canvas = document.getElementById('canvas');
    var ctx = canvas.getContext('2d');
    var raf;
    var running = false;

    var ball = {
      x: 100,
      y: 100,
      vx: 5,
      vy: 1,
      radius: 25,
      color: 'blue',
      draw: function() {
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2, true);
        ctx.closePath();
        ctx.fillStyle = this.color;
        ctx.fill();
      }
    };

    function clear() {
      ctx.fillStyle = 'rgba(255, 255, 255, 0.3)';
      ctx.fillRect(0,0,canvas.width,canvas.height);
    }

    function draw() {
      clear();
      ball.draw();
      ball.x += ball.vx;
      ball.y += ball.vy;

      if (ball.y + ball.vy > canvas.height || ball.y + ball.vy < 0) {
        ball.vy = -ball.vy;
      }
      if (ball.x + ball.vx > canvas.width || ball.x + ball.vx < 0) {
        ball.vx = -ball.vx;
      }

      raf = window.requestAnimationFrame(draw);
    }

    canvas.addEventListener('mousemove', function(e) {
      if (!running) {
        clear();
        ball.x = e.clientX;
        ball.y = e.clientY;
        ball.draw();
      }
    });

    canvas.addEventListener('click', function(e) {
      if (!running) {
        raf = window.requestAnimationFrame(draw);
        running = true;
      }
    });

    canvas.addEventListener('mouseout', function(e) {
      window.cancelAnimationFrame(raf);
      running = false;
    });

    ball.draw();

Move the ball using your mouse and release it with a click.

## Breakout

This short chapter only explains some techniques to create more advanced animations. There are many more! How about adding a paddle, some bricks, and turn this demo into a [Breakout](https://en.wikipedia.org/wiki/Breakout_%28video_game%29) game? Check out our [Game development](https://developer.mozilla.org/en-US/docs/Games) area for more gaming related articles.

## See also

- [`window.requestAnimationFrame()`](../../window/requestanimationframe)
- [Efficient animation for web games](https://developer.mozilla.org/en-US/docs/Games/Techniques/Efficient_animation_for_web_games)

<!-- -->

- <a href="basic_animations" class="button minimal">« Previous</a>
- <a href="pixel_manipulation_with_canvas" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Advanced_animations" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Advanced_animations</a>
