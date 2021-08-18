# Basic animations

- <a href="compositing" class="button minimal">« Previous</a>
- <a href="advanced_animations" class="button minimal">Next »</a>

Since we're using JavaScript to control [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) elements, it's also very easy to make (interactive) animations. In this chapter we will take a look at how to do some basic animations.

Probably the biggest limitation is, that once a shape gets drawn, it stays that way. If we need to move it we have to redraw it and everything that was drawn before it. It takes a lot of time to redraw complex frames and the performance depends highly on the speed of the computer it's running on.

## Basic animation steps

These are the steps you need to take to draw a frame:

1.  **Clear the canvas**  
    Unless the shapes you'll be drawing fill the complete canvas (for instance a backdrop image), you need to clear any shapes that have been drawn previously. The easiest way to do this is using the [`clearRect()`](../../canvasrenderingcontext2d/clearrect) method.
2.  **Save the canvas state**  
    If you're changing any setting (such as styles, transformations, etc.) which affect the canvas state and you want to make sure the original state is used each time a frame is drawn, you need to save that original state.
3.  **Draw animated shapes**  
    The step where you do the actual frame rendering.
4.  **Restore the canvas state**  
    If you've saved the state, restore it before drawing a new frame.

## Controlling an animation

Shapes are drawn to the canvas by using the canvas methods directly or by calling custom functions. In normal circumstances, we only see these results appear on the canvas when the script finishes executing. For instance, it isn't possible to do an animation from within a `for` loop.

That means we need a way to execute our drawing functions over a period of time. There are two ways to control an animation like this.

### Scheduled updates

First there's the [`window.setInterval()`](../../windoworworkerglobalscope/setinterval), [`window.setTimeout()`](../../windoworworkerglobalscope/settimeout), and [`window.requestAnimationFrame()`](../../window/requestanimationframe) functions, which can be used to call a specific function over a set period of time.

[`setInterval(function, delay)`](../../windoworworkerglobalscope/setinterval)  
Starts repeatedly executing the function specified by `function` every `delay` milliseconds.

[`setTimeout(function, delay)`](../../windoworworkerglobalscope/settimeout)  
Executes the function specified by `function` in `delay` milliseconds.

[`requestAnimationFrame(callback)`](../../window/requestanimationframe)  
Tells the browser that you wish to perform an animation and requests that the browser call a specified function to update an animation before the next repaint.

If you don't want any user interaction you can use the `setInterval()` function which repeatedly executes the supplied code. If we wanted to make a game, we could use keyboard or mouse events to control the animation and use `setTimeout()`. By setting [`EventListener`](../../eventlistener)s, we catch any user interaction and execute our animation functions.

In the examples below, we'll use the [`window.requestAnimationFrame()`](../../window/requestanimationframe) method to control the animation. The `requestAnimationFrame` method provides a smoother and more efficient way for animating by calling the animation frame when the system is ready to paint the frame. The number of callbacks is usually 60 times per second and may be reduced to a lower rate when running in background tabs. For more information about the animation loop, especially for games, see the article [Anatomy of a video game](https://developer.mozilla.org/en-US/docs/Games/Anatomy) in our [Game development zone](https://developer.mozilla.org/en-US/docs/Games).

## An animated solar system

This example animates a small model of our solar system.

    var sun = new Image();
    var moon = new Image();
    var earth = new Image();
    function init() {
      sun.src = 'https://mdn.mozillademos.org/files/1456/Canvas_sun.png';
      moon.src = 'https://mdn.mozillademos.org/files/1443/Canvas_moon.png';
      earth.src = 'https://mdn.mozillademos.org/files/1429/Canvas_earth.png';
      window.requestAnimationFrame(draw);
    }

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');

      ctx.globalCompositeOperation = 'destination-over';
      ctx.clearRect(0, 0, 300, 300); // clear canvas

      ctx.fillStyle = 'rgba(0, 0, 0, 0.4)';
      ctx.strokeStyle = 'rgba(0, 153, 255, 0.4)';
      ctx.save();
      ctx.translate(150, 150);

      // Earth
      var time = new Date();
      ctx.rotate(((2 * Math.PI) / 60) * time.getSeconds() + ((2 * Math.PI) / 60000) * time.getMilliseconds());
      ctx.translate(105, 0);
      ctx.fillRect(0, -12, 40, 24); // Shadow
      ctx.drawImage(earth, -12, -12);

      // Moon
      ctx.save();
      ctx.rotate(((2 * Math.PI) / 6) * time.getSeconds() + ((2 * Math.PI) / 6000) * time.getMilliseconds());
      ctx.translate(0, 28.5);
      ctx.drawImage(moon, -3.5, -3.5);
      ctx.restore();

      ctx.restore();

      ctx.beginPath();
      ctx.arc(150, 150, 105, 0, Math.PI * 2, false); // Earth orbit
      ctx.stroke();

      ctx.drawImage(sun, 0, 0, 300, 300);

      window.requestAnimationFrame(draw);
    }

    init();

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

## An animated clock

This example draws an animated clock, showing your current time.

    function clock() {
      var now = new Date();
      var ctx = document.getElementById('canvas').getContext('2d');
      ctx.save();
      ctx.clearRect(0, 0, 150, 150);
      ctx.translate(75, 75);
      ctx.scale(0.4, 0.4);
      ctx.rotate(-Math.PI / 2);
      ctx.strokeStyle = 'black';
      ctx.fillStyle = 'white';
      ctx.lineWidth = 8;
      ctx.lineCap = 'round';

      // Hour marks
      ctx.save();
      for (var i = 0; i < 12; i++) {
        ctx.beginPath();
        ctx.rotate(Math.PI / 6);
        ctx.moveTo(100, 0);
        ctx.lineTo(120, 0);
        ctx.stroke();
      }
      ctx.restore();

      // Minute marks
      ctx.save();
      ctx.lineWidth = 5;
      for (i = 0; i < 60; i++) {
        if (i % 5!= 0) {
          ctx.beginPath();
          ctx.moveTo(117, 0);
          ctx.lineTo(120, 0);
          ctx.stroke();
        }
        ctx.rotate(Math.PI / 30);
      }
      ctx.restore();

      var sec = now.getSeconds();
      var min = now.getMinutes();
      var hr  = now.getHours();
      hr = hr >= 12 ? hr - 12 : hr;

      ctx.fillStyle = 'black';

      // write Hours
      ctx.save();
      ctx.rotate(hr * (Math.PI / 6) + (Math.PI / 360) * min + (Math.PI / 21600) *sec);
      ctx.lineWidth = 14;
      ctx.beginPath();
      ctx.moveTo(-20, 0);
      ctx.lineTo(80, 0);
      ctx.stroke();
      ctx.restore();

      // write Minutes
      ctx.save();
      ctx.rotate((Math.PI / 30) * min + (Math.PI / 1800) * sec);
      ctx.lineWidth = 10;
      ctx.beginPath();
      ctx.moveTo(-28, 0);
      ctx.lineTo(112, 0);
      ctx.stroke();
      ctx.restore();

      // Write seconds
      ctx.save();
      ctx.rotate(sec * Math.PI / 30);
      ctx.strokeStyle = '#D40000';
      ctx.fillStyle = '#D40000';
      ctx.lineWidth = 6;
      ctx.beginPath();
      ctx.moveTo(-30, 0);
      ctx.lineTo(83, 0);
      ctx.stroke();
      ctx.beginPath();
      ctx.arc(0, 0, 10, 0, Math.PI * 2, true);
      ctx.fill();
      ctx.beginPath();
      ctx.arc(95, 0, 10, 0, Math.PI * 2, true);
      ctx.stroke();
      ctx.fillStyle = 'rgba(0, 0, 0, 0)';
      ctx.arc(0, 0, 3, 0, Math.PI * 2, true);
      ctx.fill();
      ctx.restore();

      ctx.beginPath();
      ctx.lineWidth = 14;
      ctx.strokeStyle = '#325FA2';
      ctx.arc(0, 0, 142, 0, Math.PI * 2, true);
      ctx.stroke();

      ctx.restore();

      window.requestAnimationFrame(clock);
    }

    window.requestAnimationFrame(clock);

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

## A looping panorama

In this example, a panorama is scrolled left-to-right. We're using [an image of Yosemite National Park](https://commons.wikimedia.org/wiki/File:Capitan_Meadows,_Yosemite_National_Park.jpg) we took from Wikipedia, but you could use any image that's larger than the canvas.

    var img = new Image();

    // User Variables - customize these to change the image being scrolled, its
    // direction, and the speed.

    img.src = 'https://mdn.mozillademos.org/files/4553/Capitan_Meadows,_Yosemite_National_Park.jpg';
    var CanvasXSize = 800;
    var CanvasYSize = 200;
    var speed = 30; // lower is faster
    var scale = 1.05;
    var y = -4.5; // vertical offset

    // Main program

    var dx = 0.75;
    var imgW;
    var imgH;
    var x = 0;
    var clearX;
    var clearY;
    var ctx;

    img.onload = function() {
        imgW = img.width * scale;
        imgH = img.height * scale;

        if (imgW > CanvasXSize) {
            // image larger than canvas
            x = CanvasXSize - imgW;
        }
        if (imgW > CanvasXSize) {
            // image width larger than canvas
            clearX = imgW;
        } else {
            clearX = CanvasXSize;
        }
        if (imgH > CanvasYSize) {
            // image height larger than canvas
            clearY = imgH;
        } else {
            clearY = CanvasYSize;
        }

        // get canvas context
        ctx = document.getElementById('canvas').getContext('2d');

        // set refresh rate
        return setInterval(draw, speed);
    }

    function draw() {
        ctx.clearRect(0, 0, clearX, clearY); // clear the canvas

        // if image is <= Canvas Size
        if (imgW <= CanvasXSize) {
            // reset, start from beginning
            if (x > CanvasXSize) {
                x = -imgW + x;
            }
            // draw additional image1
            if (x > 0) {
                ctx.drawImage(img, -imgW + x, y, imgW, imgH);
            }
            // draw additional image2
            if (x - imgW > 0) {
                ctx.drawImage(img, -imgW * 2 + x, y, imgW, imgH);
            }
        }

        // image is > Canvas Size
        else {
            // reset, start from beginning
            if (x > (CanvasXSize)) {
                x = CanvasXSize - imgW;
            }
            // draw additional image
            if (x > (CanvasXSize-imgW)) {
                ctx.drawImage(img, x - imgW + 1, y, imgW, imgH);
            }
        }
        // draw image
        ctx.drawImage(img, x, y,imgW, imgH);
        // amount to move
        x += dx;
    }

Below is the [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) in which the image is scrolled. Note that the width and height specified here must match the values of the `CanvasXZSize` and `CanvasYSize` variables in the JavaScript code.

    <canvas id="canvas" width="800" height="200"></canvas>

## Mouse Following Animation

    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <meta http-equiv="X-UA-Compatible" content="ie=edge">
            <title>Document</title>
            <script>
                var cn;
                //= document.getElementById('cw');
                var c;
                var u = 10;
                const m = {
                    x: innerWidth / 2,
                    y: innerHeight / 2
                };
                window.onmousemove = function(e) {
                    m.x = e.clientX;
                    m.y = e.clientY;

                }
                function gc() {
                    var s = "0123456789ABCDEF";
                    var c = "#";
                    for (var i = 0; i < 6; i++) {
                        c += s[Math.ceil(Math.random() * 15)]
                    }
                    return c
                }
                var a = [];
                window.onload = function myfunction() {
                    cn = document.getElementById('cw');
                    c = cn.getContext('2d');

                    for (var i = 0; i < 10; i++) {
                        var r = 30;
                        var x = Math.random() * (innerWidth - 2 * r) + r;
                        var y = Math.random() * (innerHeight - 2 * r) + r;
                        var t = new ob(innerWidth / 2,innerHeight / 2,5,"red",Math.random() * 200 + 20,2);
                        a.push(t);
                    }
                    //cn.style.backgroundColor = "#700bc8";

                    c.lineWidth = "2";
                    c.globalAlpha = 0.5;
                    resize();
                    anim()
                }
                window.onresize = function() {

                    resize();

                }
                function resize() {
                    cn.height = innerHeight;
                    cn.width = innerWidth;
                    for (var i = 0; i < 101; i++) {
                        var r = 30;
                        var x = Math.random() * (innerWidth - 2 * r) + r;
                        var y = Math.random() * (innerHeight - 2 * r) + r;
                        a[i] = new ob(innerWidth / 2,innerHeight / 2,4,gc(),Math.random() * 200 + 20,0.02);

                    }
                    //  a[0] = new ob(innerWidth / 2, innerHeight / 2, 40, "red", 0.05, 0.05);
                    //a[0].dr();
                }
                function ob(x, y, r, cc, o, s) {
                    this.x = x;
                    this.y = y;
                    this.r = r;
                    this.cc = cc;
                    this.theta = Math.random() * Math.PI * 2;
                    this.s = s;
                    this.o = o;
                    this.t = Math.random() * 150;

                    this.o = o;
                    this.dr = function() {
                        const ls = {
                            x: this.x,
                            y: this.y
                        };
                        this.theta += this.s;
                        this.x = m.x + Math.cos(this.theta) * this.t;
                        this.y = m.y + Math.sin(this.theta) * this.t;
                        c.beginPath();
                        c.lineWidth = this.r;
                        c.strokeStyle = this.cc;
                        c.moveTo(ls.x, ls.y);
                        c.lineTo(this.x, this.y);
                        c.stroke();
                        c.closePath();

                    }
                }
                function anim() {
                    requestAnimationFrame(anim);
                    c.fillStyle = "rgba(0,0,0,0.05)";
                    c.fillRect(0, 0, cn.width, cn.height);
                    a.forEach(function(e, i) {
                        e.dr();
                    });

                }
            </script>
            <style>
                #cw {
                    position: fixed;
                    z-index: -1;
                }

                body {
                    margin: 0;
                    padding: 0;
                    background-color: rgba(0,0,0,0.05);
                }
            </style>
        </head>
        <body>
            <canvas id="cw"></canvas>
        </body>
    </html>

##### Output

<table><colgroup><col style="width: 100%" /></colgroup><tbody><tr class="odd"><td><p><a href="https://kunalverma94.github.io/gallery/gags/beyblade.html"><img src="data:image/jpeg;base64,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" alt="beyblade" width="399" height="298" /></a></p></td></tr></tbody></table>

## Snake Game

    <!DOCTYPE html>
    <html lang="en">

    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width,initial-scale=1">
        <meta http-equiv="X-UA-Compatible" content="ie=edge">
        <title>Nokia 1100:snake..Member berries</title>
    </head>

    <body>
        <div class="keypress hide">
            <div class="up" onclick="emit(38)">&#8593;</div>
            <div class="right" onclick="emit(39)">&#8594;</div>
            <div class="left" onclick="emit(37)">&#8592;</div>
            <div class="down" onclick="emit(40)">&#8595;</div>
        </div>
        <div class="banner" id="selector">
            <div>
                Time :<span id="time">0</span>
            </div>
            <div>LousyGames ©</div>
            <div>
                Score :<span id="score">0</span>
            </div>
            <div class="touch off" onclick="touch(this)">touch</div>
        </div>
        <canvas id="main"></canvas>
    </body>
    <style>
        body {
            margin: 0;
            overflow: hidden;
            background: #000
        }

        .banner {
            text-align: center;
            color: #fff;
            background: #3f51b5;
            line-height: 29px;
            position: fixed;
            left: 0;
            top: 0;
            right: 0;
            font-family: monospace;
            height: 30px;
            opacity: .4;
            display: flex;
            transition: .5s
        }

        .banner:hover {
            opacity: 1
        }

        div#selector>div {
            flex-basis: 30%
        }

        @keyframes diss {
            from {
                opacity: 1
            }

            to {
                opacity: 0
            }
        }

        .keypress>div {
            border: dashed 3px #fff;
            height: 48%;
            width: 48%;
            display: flex;
            align-content: center;
            justify-content: center;
            align-self: center;
            align-items: center;
            font-size: -webkit-xxx-large;
            font-weight: 900;
            color: #fff;
            transition: .5s;
            opacity: .1;
            border-radius: 7px
        }

        .keypress {
            position: fixed;
            width: 100vw;
            height: 100vh;
            top: 0;
            left: 0;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-around;
            opacity: 1;
            user-select: none
        }

        .keypress>div:hover {
            opacity: 1
        }

        .touch {
            background: #8bc34a
        }

        .off {
            background: #f44336
        }

        .hide {
            opacity: 0
        }
    </style>
    </html>

Javascript

    function tmz() {
            var e = new Date(t),
                i = new Date,
                n = Math.abs(i.getMinutes() - e.getMinutes()),
                o = Math.abs(i.getSeconds() - e.getSeconds());
            return n + " : " + o
        }

        function coll(t, e) {
            return t.x < e.x + e.w && t.x + t.w > e.x && t.y < e.y + e.h && t.h + t.y > e.y
        }

        function snake() {
            this.w = 15, this.h = 15, this.dx = 1, this.dy = 1, this.xf = 1, this.yf = 1, this.sn = [];
            for (var t = {
                x: w / 2,
                y: h / 2
            }, e = 0; e < 5; e++) this.sn.push(Object.assign({}, t)), t.x += this.w;
            this.draw = function () {
                var t = d && d.search("Arrow") > -1,
                    e = -1;
                if (t) {
                    var i = {
                        ...this.sn[0]
                    };
                    if ("ArrowUp" == d && (i.y -= this.h), "ArrowDown" == d && (i.y += this.h), "ArrowLeft" == d && (i.x -= this.w), "ArrowRight" == d && (i.x += this.w), i.x >= w ? i.x = 0 : i.x < 0 && (i.x = w - this.w), i.y > h ? i.y = 0 : i.y < 0 && (i.y = h), e = fa.findIndex(t => coll({
                        ...this.sn[0],
                        h: this.h,
                        w: this.w
                    }, t)), this.sn.unshift(i), -1 != e) return console.log(e), fa[e].renew(), void (document.getElementById("score").innerText = Number(document.getElementById("score").innerText) + 1);
                    this.sn.pop(), console.log(6)
                }
                this.sn.forEach((t, e, i) => {
                    if (0 == e || i.length - 1 == e) {
                        var n = c.createLinearGradient(t.x, t.y, t.x + this.w, t.y + this.h);
                        i.length - 1 == e ? (n.addColorStop(0, "black"), n.addColorStop(1, "#8BC34A")) : (n.addColorStop(0, "#8BC34A"), n.addColorStop(1, "white")), c.fillStyle = n
                    } else c.fillStyle = "#8BC34A";
                    c.fillRect(t.x, t.y, this.w, this.h), c.strokeStyle = "#E91E63", c.font = "30px serif", c.strokeStyle = "#9E9E9E", i.length - 1 != e && 0 != e && c.strokeRect(t.x, t.y, this.w, this.h), 0 == e && (c.beginPath(), c.fillStyle = "#F44336", c.arc(t.x + 10, t.y + 2, 5, 360, 0), c.fill()), c.arc(t.x + 10, t.y + 2, 5, 360, 0), c.fill(), c.beginPath()
                })
            }
        }

        function gc() {
            for (var t = "0123456789ABCDEF", e = "#", i = 0; i < 6; i++) e += t[Math.ceil(15 * Math.random())];
            return e
        }

        function food() {
            this.x = 0, this.y = 0, this.b = 10, this.w = this.b, this.h = this.b, this.color = gc(), this.renew = function () {
                this.x = Math.floor(Math.random() * (w - 200) + 10), this.y = Math.floor(Math.random() * (h - 200) + 30), this.color = gc()
            }, this.renew(), this.put = (() => {
                c.fillStyle = this.color, c.arc(this.x, this.y, this.b - 5, 0, 2 * Math.PI), c.fill(), c.beginPath(), c.arc(this.x, this.y, this.b - 5, 0, Math.PI), c.strokeStyle = "green", c.lineWidth = 10, c.stroke(), c.beginPath(), c.lineWidth = 1
            })
        }

        function init() {
            cc.height = h, cc.width = w, c.fillRect(0, 0, w, innerHeight);
            for (var t = 0; t < 10; t++) fa.push(new food);
            s = new snake(w / 2, h / 2, 400, 4, 4), anima()
        }

        function anima() {
            c.fillStyle = "rgba(0,0,0,0.11)", c.fillRect(0, 0, cc.width, cc.height), fa.forEach(t => t.put()), s.draw(), document.getElementById("time").innerText = tmz(), setTimeout(() => {
                requestAnimationFrame(anima)
            }, fw)
        }

        function emit(t) {
            key.keydown(t)
        }

        function touch(t) {
            t.classList.toggle("off"), document.getElementsByClassName("keypress")[0].classList.toggle("hide")
        }
        var t = new Date + "",
            d = void 0,
            cc = document.getElementsByTagName("canvas")[0],
            c = cc.getContext("2d");
        key = {}, key.keydown = function (t) {
            var e = document.createEvent("KeyboardEvent");
            Object.defineProperty(e, "keyCode", {
                get: function () {
                    return this.keyCodeVal
                }
            }), Object.defineProperty(e, "key", {
                get: function () {
                    return 37 == this.keyCodeVal ? "ArrowLeft" : 38 == this.keyCodeVal ? "ArrowUp" : 39 == this.keyCodeVal ? "ArrowRight" : "ArrowDown"
                }
            }), Object.defineProperty(e, "which", {
                get: function () {
                    return this.keyCodeVal
                }
            }), e.initKeyboardEvent ? e.initKeyboardEvent("keydown", !0, !0, document.defaultView, !1, !1, !1, !1, t, t) : e.initKeyEvent("keydown", !0, !0, document.defaultView, !1, !1, !1, !1, t, 0), e.keyCodeVal = t, e.keyCode !== t && alert("keyCode mismatch " + e.keyCode + "(" + e.which + ")"), document.dispatchEvent(e)
        };
        var o, s, h = innerHeight,
            w = innerWidth,
            fw = 60,
            fa = [];
        window.onkeydown = function (t) {
            var e = t.key;
            (e.search("Arrow") > -1 || "1" == e) && (d = t.key), "i" != e && "I" != e || (console.log("inc"), fw -= 10), "d" != e && "D" != e || (console.log("dec"), fw += 10)
        }, init();

##### Output

[<img src="data:image/jpeg;base64,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" alt="Snake game" width="600" height="400" />](https://kunalverma94.github.io/pokemon/snake.html)

## Other examples

[A basic ray-caster](../a_basic_ray-caster)  
A good example of how to do animations using keyboard controls.

[Advanced animations](advanced_animations)  
We will have a look at some advanced animation techniques and physics in the next chapter.

- <a href="compositing" class="button minimal">« Previous</a>
- <a href="advanced_animations" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_animations" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Basic_animations</a>
