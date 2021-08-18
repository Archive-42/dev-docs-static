# Drawing shapes with canvas

- <a href="basic_usage" class="button minimal">« Previous</a>
- <a href="applying_styles_and_colors" class="button minimal">Next »</a>

Now that we have set up our [canvas environment](basic_usage), we can get into the details of how to draw on the canvas. By the end of this article, you will have learned how to draw rectangles, triangles, lines, arcs and curves, providing familiarity with some of the basic shapes. Working with paths is essential when drawing objects onto the canvas and we will see how that can be done.

## The grid

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAANwAAADcCAMAAAAshD+zAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAD9QTFRF////+Pj4+vr6zMzM5eXl/Pz89/f39vb2MV6g/v7+AAAApqamfX19QkJCvLy83Nzc7e3tJSUlmJiYYWFhrKysmmu/mwAABCVJREFUeNrt3AuTmyAUBWAVjZUCl4f//7cWNHa20aSah4E752THTt00yzcHgnE6W1UIgiAIgiBZp7Ykig7Z+g5t6IlsX3QsUX+nN2r74tPSZneDpZ5ByG42V/qcXGbmJk70LCKAY45rtdYtV5wWvdBMcW2CFVfdTpxR8aAMU1yIh8AUd3Hx4Li+ofhggme7z5niVtwOXDkbXBtnlhGHcAVtcFq0//ZwB3dZ0up40O2lhJBW/p8T/8MZFQ/KxIPMFiWXoSl9OYYL8RBMeoWsMw02uGO4Oj1/+jdy43nt43Ny5/OeP/f7Z3NGe3UId5k2uLxxSzRdXHsIF1eduTyHi7PlTNyorqvoAO7vss0dN62iujkJd/a0XAU44IADDjjggAMOOOCAA243rl1HPD4ndz7v+XNoDridP5jia1qTMa5eZz9O2kqFk3D1o3wAVwVVOeKKI+l1xRVXBWn44q7F8cS5kS/OuIovTo2McWdeoQAHHHDAAQfcm3BZ3kNBc8/i7GgrI7iuuRCEY4uzTvrSpmWzetzBDd7Zb+KaB4+XmxtlcFybE1LEZbc9mDP+e9Rnm7Ppa/ge7qNr7tv73Puak3L3D05PLWjNHc+v55N/c2fgvrbmymouQxyaQ3NoDs3l1tzxex4v4D56D6WY5qax1XMb7NZclNVeORVDO5tr1skTl0bWLbjbIXPA3Q1w+eNU+oRlmOKcZdycZjotu6C1di4eBMPmhLnG4t0SuKxw892221XHBBdMI3RjNNutQJmGJ85RYzVZxxI3Oi2VlyPPd0trqCGLrWATl+U9lGlOqkax/bB6GNetHpni0tCW3A6ZxZr7CWTYHGlJgWtzOl55aa5rLtLS5dfNmPk0R84ybU5o6caGY3PLm2XHep9juuZGfeTuV2HNuXG6+8WxuaM3ZYtprml8vGZ2YbpwZtdc59U1/K5Qmo7xp4Lup2lfc906eeK6RwFuxmV5DwXNAQcccMABBxxwB3GfPwcccMABBxxwT+GG1SNT3PDggebm5j71O01e+n0oaA5rDs2hOTSH5tAcmkNzaA7NoTk0h+ZYNDeskydueBTgZlyW91DQHHDAAQcccMD9H/c7x7wLNxQX4IA7GGPmP1UOOCnfpFtQ6vMT4nSckOIvzlMmuHePIuG04YCrTJhWl/dRNAyd1yGoWKKLL6u0+j7utUiychzcXJXXltzSnLGOCsep4J32ep4BCfVjWmpTOM5KJ1wqLmlCnJ0hG1wXRzPQ+FJ1On3NOONGL/NpzqehvNSnHQfrl12blE+beNoKrjvCmbibv3eDtiZUpUXsPGuCs2xx8U2gYourlAEOuOxwJQY44IDLAtdwsN35xRNkOeAsbZ9uOeDa7YpqBtUNlurt7/TU2qLXXWNb6u99s7Ykig7Z+kGrFYIgCIIgyPfzB5Lb7mr+ARrCAAAAAElFTkSuQmCC" class="internal" width="220" height="220" />Before we can start drawing, we need to talk about the canvas grid or **coordinate space**. Our HTML skeleton from the previous page had a canvas element 150 pixels wide and 150 pixels high. To the right, you see this canvas with the default grid overlayed. Normally 1 unit in the grid corresponds to 1 pixel on the canvas. The origin of this grid is positioned in the _top left_ corner at coordinate (0,0). All elements are placed relative to this origin. So the position of the top left corner of the blue square becomes x pixels from the left and y pixels from the top, at coordinate (x,y). Later in this tutorial we'll see how we can translate the origin to a different position, rotate the grid and even scale it, but for now we'll stick to the default.

## Drawing rectangles

Unlike [SVG](https://developer.mozilla.org/en-US/docs/Glossary/SVG), [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) only supports two primitive shapes: rectangles and paths (lists of points connected by lines). All other shapes must be created by combining one or more paths. Luckily, we have an assortment of path drawing functions which make it possible to compose very complex shapes.

First let's look at the rectangle. There are three functions that draw rectangles on the canvas:

[`fillRect(x, y, width, height)`](../../canvasrenderingcontext2d/fillrect)  
Draws a filled rectangle.

[`strokeRect(x, y, width, height)`](../../canvasrenderingcontext2d/strokerect)  
Draws a rectangular outline.

[`clearRect(x, y, width, height)`](../../canvasrenderingcontext2d/clearrect)  
Clears the specified rectangular area, making it fully transparent.

Each of these three functions takes the same parameters. `x` and `y` specify the position on the canvas (relative to the origin) of the top-left corner of the rectangle. `width` and `height` provide the rectangle's size.

Below is the `draw()` function from the previous page, but now it is making use of these three functions.

### Rectangular shape example

    function draw() {
      var canvas = document.getElementById('canvas');
      if (canvas.getContext) {
        var ctx = canvas.getContext('2d');

        ctx.fillRect(25, 25, 100, 100);
        ctx.clearRect(45, 45, 60, 60);
        ctx.strokeRect(50, 50, 50, 50);
      }
    }

This example's output is shown below.

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAL4AAAC+BAMAAAB5WqiuAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAABtQTFRF/Pz8////+Pj4/v7+9/f3+vr6AAAAzMzM4eHhnREajwAAAZRJREFUeNrt3L9Lw0AYxvGApK4VBZ2DrRmFip2VqB1LMNWxROusVdHVEjF/tr+g3L3kQlve07Z8H0qW3H3yNNx0cAm2/CbAx8f37ccfL7p5fTf9o7JIdNMrTww/1ua/HjAx/DLRT/mH/pMH/wJ/qfxekhRKl+8f7x8fHx8fHx8f38z53by5/U9/HEXRvnHvtD23n0eWHkUHwreyiC+Cj4+Pj48/bom03fMcPXJJWH46+zwz5rjUQ/+WQv+0LivR37lmlN6/6y+0lfrnrsXjt39Lrb9r8dCf/j/X50xkMJ03yrJRVp2BGGfnCh8fHx8fvy9izAvDUb86A2ucvGv5YW3/cJb+If3pT3/6L2H/+0CkMZ03DIJhUJ2GGGdnEx9/LXzn/pKSXxP8VfdnzXr7hyIL+JLo1vTfoD/96U9/+i9F/8eOyPHc/o0kunW+QvDx8fHx8fHr/QcPJ0938fHxf/f/PfjG/n+z0OebPfP8sof+5vnl+E2d3zPPd++UZ8r8pXU+vXOtfr5+4vf7ANt8PwEf37v/CfwK86oaSIlGAAAAAElFTkSuQmCC" class="internal" /></td><td></td></tr></tbody></table>

The `fillRect()` function draws a large black square 100 pixels on each side. The `clearRect()` function then erases a 60x60 pixel square from the center, and then `strokeRect()` is called to create a rectangular outline 50x50 pixels within the cleared square.

In upcoming pages we'll see two alternative methods for `clearRect()`, and we'll also see how to change the color and stroke style of the rendered shapes.

Unlike the path functions we'll see in the next section, all three rectangle functions draw immediately to the canvas.

## Drawing paths

Now let's look at paths. A path is a list of points, connected by segments of lines that can be of different shapes, curved or not, of different width and of different color. A path, or even a subpath, can be closed. To make shapes using paths, we take some extra steps:

1.  First, you create the path.
2.  Then you use [drawing commands](../../canvasrenderingcontext2d#paths) to draw into the path.
3.  Once the path has been created, you can stroke or fill the path to render it.

Here are the functions used to perform these steps:

[`beginPath()`](../../canvasrenderingcontext2d/beginpath)  
Creates a new path. Once created, future drawing commands are directed into the path and used to build the path up.

[Path methods](../../canvasrenderingcontext2d#paths)  
Methods to set different paths for objects.

[`closePath()`](../../canvasrenderingcontext2d/closepath)  
Adds a straight line to the path, going to the start of the current sub-path.

[`stroke()`](../../canvasrenderingcontext2d/stroke)  
Draws the shape by stroking its outline.

[`fill()`](../../canvasrenderingcontext2d/fill)  
Draws a solid shape by filling the path's content area.

The first step to create a path is to call the `beginPath()`. Internally, paths are stored as a list of sub-paths (lines, arcs, etc) which together form a shape. Every time this method is called, the list is reset and we can start drawing new shapes.

**Note:** When the current path is empty, such as immediately after calling `beginPath()`, or on a newly created canvas, the first path construction command is always treated as a `moveTo()`, regardless of what it actually is. For that reason, you will almost always want to specifically set your starting position after resetting a path.

The second step is calling the methods that actually specify the paths to be drawn. We'll see these shortly.

The third, and an optional step, is to call `closePath()`. This method tries to close the shape by drawing a straight line from the current point to the start. If the shape has already been closed or there's only one point in the list, this function does nothing.

**Note:** When you call `fill()`, any open shapes are closed automatically, so you don't have to call `closePath()`. This is **not** the case when you call `stroke()`.

### Drawing a triangle

For example, the code for drawing a triangle would look something like this:

    function draw() {
      var canvas = document.getElementById('canvas');
      if (canvas.getContext) {
        var ctx = canvas.getContext('2d');

        ctx.beginPath();
        ctx.moveTo(75, 50);
        ctx.lineTo(100, 75);
        ctx.lineTo(100, 25);
        ctx.fill();
      }
    }

The result looks like this:

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAKgAAACRAgMAAAAqUBtCAAAAGXRFWHRTb2Z0d2FyZQBnbm9tZS1zY3JlZW5zaG907wO/PgAAAAxQTFRF////AAAAcHBwgYGBOZMk1AAAAJ9JREFUWMPt1jENwzAARFHLmTwYhiF4D4nwKYnwKQnzaZISeFKnSvfnN9x4paSUUkr/35vltjPtTqfTxXQ7mHan0+liuh1Mu9PpdDG9pirtTqfTxfSeirQ7nU4X02eq0e50Ol1OT6fDaXNanX7HGh1Om9Pq9BmLdDhtTqvTe6zS4bQ5rU6vsUyH0+a0Oi2n0+G0Oa1OyyvvKaWUUkrppz4iq0BTxM11tAAAAABJRU5ErkJggg==" class="internal" /></td><td></td></tr></tbody></table>

### Moving the pen

One very useful function, which doesn't actually draw anything but becomes part of the path list described above, is the `moveTo()` function. You can probably best think of this as lifting a pen or pencil from one spot on a piece of paper and placing it on the next.

[`moveTo(x, y)`](../../canvasrenderingcontext2d/moveto)  
Moves the pen to the coordinates specified by `x` and `y`.

When the canvas is initialized or `beginPath()` is called, you typically will want to use the `moveTo()` function to place the starting point somewhere else. We could also use `moveTo()` to draw unconnected paths. Take a look at the smiley face below.

To try this for yourself, you can use the code snippet below. Just paste it into the `draw()` function we saw earlier.

    function draw() {
      var canvas = document.getElementById('canvas');
      if (canvas.getContext) {
         var ctx = canvas.getContext('2d');

        ctx.beginPath();
        ctx.arc(75, 75, 50, 0, Math.PI * 2, true); // Outer circle
        ctx.moveTo(110, 75);
        ctx.arc(75, 75, 35, 0, Math.PI, false);  // Mouth (clockwise)
        ctx.moveTo(65, 65);
        ctx.arc(60, 65, 5, 0, Math.PI * 2, true);  // Left eye
        ctx.moveTo(95, 65);
        ctx.arc(90, 65, 5, 0, Math.PI * 2, true);  // Right eye
        ctx.stroke();
      }
    }

The result looks like this:

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

If you'd like to see the connecting lines, you can remove the lines that call `moveTo()`.

**Note:** To learn more about the `arc()` function, see the [Arcs](#arcs) section below.

### Lines

For drawing straight lines, use the `lineTo()` method.

[`lineTo(x, y)`](../../canvasrenderingcontext2d/lineto)  
Draws a line from the current drawing position to the position specified by `x` and `y`.

This method takes two arguments, `x` and `y`, which are the coordinates of the line's end point. The starting point is dependent on previously drawn paths, where the end point of the previous path is the starting point for the following, etc. The starting point can also be changed by using the `moveTo()` method.

The example below draws two triangles, one filled and one outlined.

    function draw() {
      var canvas = document.getElementById('canvas');
      if (canvas.getContext) {
        var ctx = canvas.getContext('2d');

        // Filled triangle
        ctx.beginPath();
        ctx.moveTo(25, 25);
        ctx.lineTo(105, 25);
        ctx.lineTo(25, 105);
        ctx.fill();

        // Stroked triangle
        ctx.beginPath();
        ctx.moveTo(125, 125);
        ctx.lineTo(125, 45);
        ctx.lineTo(45, 125);
        ctx.closePath();
        ctx.stroke();
      }
    }

This starts by calling `beginPath()` to start a new shape path. We then use the `moveTo()` method to move the starting point to the desired position. Below this, two lines are drawn which make up two sides of the triangle.

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAL4AAAC+CAMAAAC8qkWvAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAFdQTFRFAAAA+Pj4/v7+/f39+fn5paWl+vr6////9vb2zMzM/Pz86urq2NjY8vLyLCws4eHhvb29Hh4eOzs7YmJim5ubSUlJ0dHRVVVVrq6ujY2NcHBwfn5+Dg4Onzzk0QAAA1JJREFUeNrt3d2OokAQBWBt0UIbRAVRxPd/zh2Thc3sgFbTP1U1qeOtF19OCOnjhb0C0VkpX/nKV77ylS+Un9mi3bNOW9hsjl8WlS1z1iltVZTT/KywuYDYIpvk2yoXkcpO8mWU/6p/kt+WMvhlO8nf50KyV77yY/G3LIPnczzeKF/5yv+l/PXfD1P+wNP2tX1tX9vX9rV9bV/b1/a1fW1f2/9t7a/Cpk/cPqH+c/vrIWn4vePDM/JY8DuQzO9AMr8DyfwOJPMbkMxvQDK/Acn8BiTzF+qZ8BcfB1nwlx9mOfA9juIM+HeQzPfR0/O99OR8P/1nfjYkCv/ku3VHHgXfV0/Kf57A4JQ9Q/4T273pV/z4aD08GPId9B2w4zvp2fGfe+xz/9Jz43/pke+cugN2fHT3UDfAju+kN9z4aP2hbn6CqPnP1lnPiI/Wb24NsOM/C2z3ty2w458X6T34uyEh+Gh9dvu2Y+b5Iy8BH61ff9fz4OO7v/63ITnwz9VSPQe+h54BH63Prz/P0uR8J73hxsfrL1M7hph/9NMT888WqS+n9bT8o6+elI/Vm1k9Jd+h+9kdQ8fH64/zK4yMj9bb45tfH6j4Tnrg1v6xROvfbkga/iWQnoYfTE/Cx+qNPX7aMQR8h+4/rrD0/EuO1Fef9en5eD1mAafmX4PqU/Md9KglkJZ/zZDvHKQ+LR+rx3aflo/WF+gFnJB/C69PyMfr0fs9If92QOstJOAfhqD4aH3ron/DH3kh+JH0ifg1Um8c9Wn4WD3sHfVJ+DXE0qfgR9Qn4GP1mz16vyfkP9DdX9z10flo/WmJPjY/sj4yP7Y+Lr/H63Pgxjfx9VHbR+uvS/Uc+Pflegb8O3pDBuVvhmzp9G/4Iy8q309Pzd/evPTEfF89LX+L3pAc+f56Sn5Te+sJ+SH0dPwgejJ+UwOI5ZtAeiJ+F0hPw+8eIJj/pTdi+SZc9xT8PqA+Pb/vgQXfDHHi94H/8WmWP/KC8lNF+cpXvvKVr3zlK1/5yle+8pWvfHf+v2+y5E9Ala/80HyWQfOZR/nKD8xvdzL0u+kLaotShN6U09cD20pG+zOXM2eFlaCfuxr7dTF5yfz535WzF5NLvxZeYJSvfOUrX/nKF5Q/rLuAU45oCk0AAAAASUVORK5CYII=" class="internal" /></td><td></td></tr></tbody></table>

You'll notice the difference between the filled and stroked triangle. This is, as mentioned above, because shapes are automatically closed when a path is filled, but not when they are stroked. If we left out the `closePath()` for the stroked triangle, only two lines would have been drawn, not a complete triangle.

### Arcs

To draw arcs or circles, we use the `arc()` or `arcTo()` methods.

[`arc(x, y, radius, startAngle, endAngle, counterclockwise)`](../../canvasrenderingcontext2d/arc)  
Draws an arc which is centered at _(x, y)_ position with radius _r_ starting at _startAngle_ and ending at _endAngle_ going in the given direction indicated by _counterclockwise_ (defaulting to clockwise).

[`arcTo(x1, y1, x2, y2, radius)`](../../canvasrenderingcontext2d/arcto)  
Draws an arc with the given control points and radius, connected to the previous point by a straight line.

Let's have a more detailed look at the `arc` method, which takes six parameters: `x` and `y` are the coordinates of the center of the circle on which the arc should be drawn. `radius` is self-explanatory. The `startAngle` and `endAngle` parameters define the start and end points of the arc in radians, along the curve of the circle. These are measured from the x axis. The `counterclockwise` parameter is a Boolean value which, when `true`, draws the arc counterclockwise; otherwise, the arc is drawn clockwise.

**Note**: Angles in the `arc` function are measured in radians, not degrees. To convert degrees to radians you can use the following JavaScript expression: `radians = (Math.PI/180)*degrees`.

The following example is a little more complex than the ones we've seen above. It draws 12 different arcs all with different angles and fills.

The two [`for` loops](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for) are for looping through the rows and columns of arcs. For each arc, we start a new path by calling `beginPath()`. In the code, each of the parameters for the arc is in a variable for clarity, but you wouldn't necessarily do that in real life.

The `x` and `y` coordinates should be clear enough. `radius` and `startAngle` are fixed. The `endAngle` starts at 180 degrees (half a circle) in the first column and is increased by steps of 90 degrees, culminating in a complete circle in the last column.

The statement for the `clockwise` parameter results in the first and third row being drawn as clockwise arcs and the second and fourth row as counterclockwise arcs. Finally, the `if` statement makes the top half stroked arcs and the bottom half filled arcs.

**Note:** This example requires a slightly larger canvas than the others on this page: 150 x 200 pixels.

    function draw() {
      var canvas = document.getElementById('canvas');
      if (canvas.getContext) {
        var ctx = canvas.getContext('2d');

        for (var i = 0; i < 4; i++) {
          for (var j = 0; j < 3; j++) {
            ctx.beginPath();
            var x = 25 + j * 50; // x coordinate
            var y = 25 + i * 50; // y coordinate
            var radius = 20; // Arc radius
            var startAngle = 0; // Starting point on circle
            var endAngle = Math.PI + (Math.PI * j) / 2; // End point on circle
            var counterclockwise = i % 2 !== 0; // clockwise or counterclockwise

            ctx.arc(x, y, radius, startAngle, endAngle, counterclockwise);

            if (i > 1) {
              ctx.fill();
            } else {
              ctx.stroke();
            }
          }
        }
      }
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

### Bezier and quadratic curves

The next type of paths available are [Bézier curves](https://en.wikipedia.org/wiki/B%C3%A9zier_curve), available in both cubic and quadratic varieties. These are generally used to draw complex organic shapes.

[`quadraticCurveTo(cp1x, cp1y, x, y)`](../../canvasrenderingcontext2d/quadraticcurveto)  
Draws a quadratic Bézier curve from the current pen position to the end point specified by `x` and `y`, using the control point specified by `cp1x` and `cp1y`.

[`bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y)`](../../canvasrenderingcontext2d/beziercurveto)  
Draws a cubic Bézier curve from the current pen position to the end point specified by `x` and `y`, using the control points specified by (`cp1x`, `cp1y`) and (cp2x, cp2y).

<img src="data:image/png;base64,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" class="internal" width="190" height="190" />The difference between these can best be described using the image on the right. A quadratic Bézier curve has a start and an end point (blue dots) and just one **control point** (indicated by the red dot) while a cubic Bézier curve uses two control points.

The `x` and `y` parameters in both of these methods are the coordinates of the end point. `cp1x` and `cp1y` are the coordinates of the first control point, and `cp2x` and `cp2y` are the coordinates of the second control point.

Using quadratic and cubic Bézier curves can be quite challenging, because unlike vector drawing software like Adobe Illustrator, we don't have direct visual feedback as to what we're doing. This makes it pretty hard to draw complex shapes. In the following example, we'll be drawing some simple organic shapes, but if you have the time and, most of all, the patience, much more complex shapes can be created.

There's nothing very difficult in these examples. In both cases we see a succession of curves being drawn which finally result in a complete shape.

#### Quadratic Bezier curves

This example uses multiple quadratic Bézier curves to render a speech balloon.

    function draw() {
      var canvas = document.getElementById('canvas');
      if (canvas.getContext) {
        var ctx = canvas.getContext('2d');

        // Quadratric curves example
        ctx.beginPath();
        ctx.moveTo(75, 25);
        ctx.quadraticCurveTo(25, 25, 25, 62.5);
        ctx.quadraticCurveTo(25, 100, 50, 100);
        ctx.quadraticCurveTo(50, 120, 30, 125);
        ctx.quadraticCurveTo(60, 120, 65, 100);
        ctx.quadraticCurveTo(125, 100, 125, 62.5);
        ctx.quadraticCurveTo(125, 25, 75, 25);
        ctx.stroke();
      }
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAL4AAAC+CAMAAAC8qkWvAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAFRQTFRF9vb2/Pz8+Pj4/////f39/v7++vr69/f3+fn5+/v7zMzMhoaGd3d3QkJCZmZmGRkZlZWV3d3dLCws6OjoVlZWBwcH8fHxwcHBtbW10tLSqampn5+f0cqZhgAABIJJREFUeNrt3duWoyoQBmAxHlDAkoMI+v7vuU36MOm1k4mtVhLW1H/Tdi80XwpEb2iyU9LJiE984hOf+MRPlM+tju1bJ2rL7/DLTGvrs7eOt1pnt/lc26yu35uf1ZnV/Cbf6iyJaHuTvxQ/iVh9i19Gnwbfx5vVb7NE0hKf+MQnPvGJnzy/TiTEJz7xiU984hOf+MQnPvGJ/4/wvY5jCNM0930v/pqlwTxNIYxR+1fzq3YWnTLDMIBRSjnXLZF/zbmFc0tjA8tpRnVibqsX8KvQmcF0cg7xs4x5XWe/7LQYZnm5TKgO4Oer03ag+nN7nnNe51vD+cfVegXdbz59H18rEDY/F/yYLBeyApR+Dn8CwfOj6J9fIOeVgOkZ/BlijpIIMzq/HsHi6PPawojN96Y9eOBc+VvjcflcihwvmZC4/Aw8Ij/3kGHy+eww9Tl3M2r1VUDl50Eh8utsYLj8YvCI1R9Vjhw14vH5uplhz9yzZmbbXH03YVd/cojVNy2yfnlyIVYf7YXhOxbw+Ax74ln3EXf4/FEscPSAfdhkI7+OBp9vIhafjwqfr0Y0fngGP6DxJ4fPdxMWv5rx+ZWb0arfd/jV73riE5/4B/OFxOdLQXziE/93/OpRhKzQI8XDJsQnPvGJT3zivwu/64lPfOIT/zp9h89301Z+8yh916BHhYdNtvIn9wT+mDTfRCw+Cwpdz0CjVX/E55dDjsZvDba+stCg8SM6f1UHbx37GtCrv2Z22Fp9i85vpMDjNyvuq53VXzHtb+evmNX2JVtToM38NbXZVfxVU/NmfjcjV7/rEfkV9jubB49ZfezHrpDNdj57mBo8Q0w0qy6/mc/chKi3JjBUfhMUGr6xpme4fFaaFosfoGcNMr8ZDc7ob5UZV7fdzGeNUPZwu+4V9Jw9gc8qAXN+4IiPkzTQhZXjZjd/GT8KumlnF3Abx1lIZwbjRFv+Br+TX5RLZzsYzGWZ3OdquB/jtmnvLZc7L5gzlwVzsJwuxdTyLffJHv7ZVzWs1uN5jeLHUsRB/Hw6mFuLFT9XK7ZR+2rfbb6Tf/kKDSuKr06XP/mg/99nSz7uneWUhr2c/yM/+REYapD5fZc0H/XFCJ8PNmV+a9hL+MXmdP2fYyZkgZvD+W6++sWMifFPKnwflxpYatVXVwUXXZEa3/w5t0QfO8fzB/99GExRJsa3cDWOpiK16k/u+3BWZWp81n3Nm0yDLlLje8g+j7QJBUuN776euSPMRZFY9UupPgpuHYxFYnxmlbrMmq0D6YvE+FqCaIp6lGDEk/CH8W2vQI6TVIMSsXheDuCXrTDn/w8E4ETwT5huDuRHOZwDSgZbsKfS/8IvV8Vf6K4ffXk6lUX5/OziF2q2y4+F/qrs4i/vNOVrs4//8hCf+MQnPvGJT3ziE5/4xCd+WvxUNhYlPvGJT3ziE/90ik0a+ubmBrWl9knoS39ze+DT9a7B75w7mzPz67+/b+5tjX3KtPZvPv4bf3dj8lP5/tvCt/e3hb98g/KUVLJT0iE+8YlPfOL/W/z/ABhSjq/rmP1OAAAAAElFTkSuQmCC" class="internal" /></td><td></td></tr></tbody></table>

#### Cubic Bezier curves

This example draws a heart using cubic Bézier curves.

    function draw() {
      var canvas = document.getElementById('canvas');
      if (canvas.getContext) {
        var ctx = canvas.getContext('2d');

        // Cubic curves example
        ctx.beginPath();
        ctx.moveTo(75, 40);
        ctx.bezierCurveTo(75, 37, 70, 25, 50, 25);
        ctx.bezierCurveTo(20, 25, 20, 62.5, 20, 62.5);
        ctx.bezierCurveTo(20, 80, 40, 102, 75, 120);
        ctx.bezierCurveTo(110, 102, 130, 80, 130, 62.5);
        ctx.bezierCurveTo(130, 62.5, 130, 25, 100, 25);
        ctx.bezierCurveTo(85, 25, 75, 37, 75, 40);
        ctx.fill();
      }
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAL4AAAC+CAMAAAC8qkWvAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAEhQTFRFAAAA+Pj4+/v7+fn5/v7+/////Pz89vb2/f399/f3+vr6zMzM5ubm29vbFxcXKioqPz8/DAwMeXl5wcHBo6OjVlZWZ2dnjo6O8v5yPwAABClJREFUeNrt3WuTnCoQBmBEA4yCXLzM//+ncSaVnM0eHUW7W630+3FL8Fm2QWZ1SvHj1hHMZz7zmc985t+UX1rXXDzOlgv8Sjtn9cVjndPz/HLCP67OfxTWlbN86/QdUjg7y79+5fyun1l+o2+ShvnMZz7zmc985p/Lf9wkzGc+85nPfOYzn/nMZz7zmc/8a/NtnwbfRiFi68OQerfaQjbPMfhfLaYG9jy+S158Tzv0ermF7of4rYFPDohf5OTRBTGfOM739LCpnW0QuqwzFwD8Zgn/zuD+38KOy8eHhpRfJ7GSVP7dwjzj5+NrOr4NYjXefm3hVlsES8TXrhUb0v7Xn+zjhuMdDb+JYlPinw6fImYdj8nfNvbv8fxVDyZtPd7h87UXmxPeLdLm473G5peDyEg/NXhmHD9g8/scvWiLohOZvy8m30aRx8mptdf0taj8IU8vQspsMCDy6y4TI9o2t0WHOPpBoCeg8fMHf086tNEfKPgDFt8Jkrid/HIliYaf1hz7+MbT8H2Fwu8EUToMfpGo+All9D0V3yPwCyvIYhFGv6fj9wijP9LxR4TR93R8D8/XgjAanN9Q8htwfk/J78H5iZKfwPkjJX8E5wdKfoDm14Trpoh+D7/+lJZy9NuPlD38SMmP4HxBGnD+zYuHcuoKD82X9+bXA+llC5qvnpT8J/jod5T8DpyvCRf+qMH5lMU/1OB8SflRHZ5PWD0rtbOPT7fj/7xs7uTXjorvMPhlMVxi4i7y5UqIlv5uzbGTL2luDkksPkn1OzS+IVh8RonGlxr9Q0urEfn4N4g6iciX9YhdOjUmv9Son7r8htI5wpd1g7j1iZsIR/iyRtx59hKdj1j+mwr/KF9i/bc2lJJg9KfV3583bY/z68IiXL1aK2n4rw7iSYvOJ77aGlN1wP7Yqe05yp8C68/SQ/BB/Xl6ED6gP1MPw5cN0PrTZp4Yhq+UA1n/vVPn8KUF8HurTuIrpQ/vH4JWp/GlrA7u30Ylz+O/rmCH9s+9MupUvlTd7gWo7dSuAPKn8bc7J0Cw6gL8aQu662GZJNUV+O8rcEtVOBj8usgtoKlw5GX4rxmcdeP0eQC/yDcHokyz+RLsD53JGAS+MdXWx91SYS7In36BbsMfwHdHT4PFN9X6Q/LT0FdX5U+yz98rDs4ABI0/TeFq+avFsa+mKX5p/uRb+k79aA1MMPnv/mcqKAB2j8w3Vf9tF9H2lbkP3xidvkyBmDRk3wT8r1NgKnp1M/4r7n0be3DQ/RLxX3M4YPRKxccJ85kPza9uEuYzn/nMZz7zmc985jOf+cxnPvP/Ef5dXizKfOYzn/nMZ/7r+f176Bee3//rpc3XjdHzrwe2trqFf+HlzOXXn183S6/G/qGd1Revf6nt0ovJb/5a+DuG+cxnPvOZz/wb5ScOe5ba3nhxSQAAAABJRU5ErkJggg==" class="internal" /></td><td></td></tr></tbody></table>

### Rectangles

In addition to the three methods we saw in [Drawing rectangles](#drawing_rectangles), which draw rectangular shapes directly to the canvas, there's also the `rect()` method, which adds a rectangular path to a currently open path.

[`rect(x, y, width, height)`](../../canvasrenderingcontext2d/rect)  
Draws a rectangle whose top-left corner is specified by (`x`, `y`) with the specified `width` and `height`.

Before this method is executed, the `moveTo()` method is automatically called with the parameters (x,y). In other words, the current pen position is automatically reset to the default coordinates.

### Making combinations

So far, each example on this page has used only one type of path function per shape. However, there's no limitation to the number or types of paths you can use to create a shape. So in this final example, let's combine all of the path functions to make a set of very famous game characters.

    function draw() {
      var canvas = document.getElementById('canvas');
      if (canvas.getContext) {
        var ctx = canvas.getContext('2d');

        roundedRect(ctx, 12, 12, 150, 150, 15);
        roundedRect(ctx, 19, 19, 150, 150, 9);
        roundedRect(ctx, 53, 53, 49, 33, 10);
        roundedRect(ctx, 53, 119, 49, 16, 6);
        roundedRect(ctx, 135, 53, 49, 33, 10);
        roundedRect(ctx, 135, 119, 25, 49, 10);

        ctx.beginPath();
        ctx.arc(37, 37, 13, Math.PI / 7, -Math.PI / 7, false);
        ctx.lineTo(31, 37);
        ctx.fill();

        for (var i = 0; i < 8; i++) {
          ctx.fillRect(51 + i * 16, 35, 4, 4);
        }

        for (i = 0; i < 6; i++) {
          ctx.fillRect(115, 51 + i * 16, 4, 4);
        }

        for (i = 0; i < 8; i++) {
          ctx.fillRect(51 + i * 16, 99, 4, 4);
        }

        ctx.beginPath();
        ctx.moveTo(83, 116);
        ctx.lineTo(83, 102);
        ctx.bezierCurveTo(83, 94, 89, 88, 97, 88);
        ctx.bezierCurveTo(105, 88, 111, 94, 111, 102);
        ctx.lineTo(111, 116);
        ctx.lineTo(106.333, 111.333);
        ctx.lineTo(101.666, 116);
        ctx.lineTo(97, 111.333);
        ctx.lineTo(92.333, 116);
        ctx.lineTo(87.666, 111.333);
        ctx.lineTo(83, 116);
        ctx.fill();

        ctx.fillStyle = 'white';
        ctx.beginPath();
        ctx.moveTo(91, 96);
        ctx.bezierCurveTo(88, 96, 87, 99, 87, 101);
        ctx.bezierCurveTo(87, 103, 88, 106, 91, 106);
        ctx.bezierCurveTo(94, 106, 95, 103, 95, 101);
        ctx.bezierCurveTo(95, 99, 94, 96, 91, 96);
        ctx.moveTo(103, 96);
        ctx.bezierCurveTo(100, 96, 99, 99, 99, 101);
        ctx.bezierCurveTo(99, 103, 100, 106, 103, 106);
        ctx.bezierCurveTo(106, 106, 107, 103, 107, 101);
        ctx.bezierCurveTo(107, 99, 106, 96, 103, 96);
        ctx.fill();

        ctx.fillStyle = 'black';
        ctx.beginPath();
        ctx.arc(101, 102, 2, 0, Math.PI * 2, true);
        ctx.fill();

        ctx.beginPath();
        ctx.arc(89, 102, 2, 0, Math.PI * 2, true);
        ctx.fill();
      }
    }

    // A utility function to draw a rectangle with rounded corners.

    function roundedRect(ctx, x, y, width, height, radius) {
      ctx.beginPath();
      ctx.moveTo(x, y + radius);
      ctx.lineTo(x, y + height - radius);
      ctx.arcTo(x, y + height, x + radius, y + height, radius);
      ctx.lineTo(x + width - radius, y + height);
      ctx.arcTo(x + width, y + height, x + width, y + height-radius, radius);
      ctx.lineTo(x + width, y + radius);
      ctx.arcTo(x + width, y, x + width - radius, y, radius);
      ctx.lineTo(x + radius, y);
      ctx.arcTo(x, y, x, y + radius, radius);
      ctx.stroke();
    }

The resulting image looks like this:

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAKkAAACxCAMAAACIjm3rAAAAGXRFWHRTb2Z0d2FyZQBnbm9tZS1zY3JlZW5zaG907wO/PgAAAIFQTFRF////FRUV9vb28PDwh4eHeHh4JCQkAAAAd3d3iIiIERERUVFRqKiox8fHlpaWLCwsgoKCzs7O+/v7HBwcZWVlsrKy1tbWCQkJ/v7+cXFxQUFBubm53NzcwcHBXFxcSEhIaWlpnJycOjo65eXlfHx8o6Ojra2tkJCQNDQ0jIyMYWFhFhzangAABIlJREFUeNrtnGl3qjAQhhOwIItEcWOR4q71///AWxbRIi2T26DDvfN+Ie05zHkMyTiZGWGMRCKRSCQSiUQikUi/lZ4cN9bwRbI2LhBzNBN26lyG1osUXhwQZ3wW1sTH/9j9mTHvxfr0HUfvx06aRX4/QOeG1g/QQMQ3PzX3BsOXqXXbb6tRZEezl7kpy2ojffeKqfVnwsW9XqeL4npxkC/XlR3kV1dg31fHtLieXexbf3PJLzt+v0ZH+8i2bSMd7xCRWmExtc69NzArpRM0pG+D/DJ4u7pXbWZ+UejjIi0vn8tAmDWlOkpS7Ww+CElYUCO9mA1a4yMNErNRE3xzKhpBoxgd6eSRcpluMO6osI7puJ+YQYCPdHuPaV/mqEKBL6S8wpyu46++Kftnx3/LkJaYxnD08MCRkS4L0vN4wZCT2tXTf5hWZKTR/Y56WKqYdtS+5qXs96OGk3TU4PmdA8pYatuXb1MWN5IuFwijvnUT6R5lJN3w/B2UkTTTozroVmMoSZlWWwBvWE98WZR6N63OCKc/rVJA+9SwueF8LBjDTYpSzyI120MQxaQrtyVtbXnuToq0sqiSVDsZ3Fn/mLYeDNepLQ4+kPTeokLSifEOcgVBnIoViBRqUZI0seH1tY0NcRsyFiVI9elRYv2fhK/YIpzUepfaqulBsUU46VQuO3WrHimyCCZdGXLuz19qai2CSV25h8/YOVFrEUz6EUqSOke1FsGk+7Ek6cxTaxFMKh0ZtN4gaZFIibR70oYIhUiJlHYUkf6fpOOTJGnrDZIW/8FYqj/xaX9i/v6coyRPksHrzqY9Ou/rhlQO5ewrtiiRlxpxeO+fZ9dSaI0ZNBmLkrk+JwGuUXCuD2ZRlpRpJ5FlO3/W2uFnifzpzaJKUpa3Urc0EXvzppLw9znpyqJiUvWNPlCLqisSWhxGgnMRvSWKS25qSfX98lZ14ycNLemcf61kThOkpKfHzoADSlKvqTfggJB03txvMUJHqvPm3lXDx0Y6Nr/RARmplvWvGXNdd8u5rcYGMtJslfK8tLvIXerdeIKLNPsVQHnWzLvC78bj55JCOgrLUmlcG6fA+59Iepga2ZfSrjYW+EjtYvvsamOOljSpj59LygCfxOF5SHKpj3HtffN7L4WQ9NPba9rN81djhKTfiEiJlEj/hjS8Hkyja2cwn6EkPbGkQI00vfg5IF+wIULSjyx0Wuagn2eVDJVnkWmIjrRss1/moCzQhWkXIXSIjPQaLsdRkTgJdttrrB/+nEF7TbYHHosRaZk/XGwGwFfbrOCkHfT0joQBew3FYHiZbmFt65309Cb2AZ7l9T1Qq2wnPb2BkHtrgpUywIfvoKc3mAi5vLnGW1+o0FFPryddi26dr45qfOrr+13VTdV3d3RVi1ZP2lV9Xz1pVz0T6jtmuupDUb+juupCUu+luiKdGL/y/E/sQJT9Nv1I2YtIfxmhPJO0iPpgeoz6nkqaRdLAV5o9RtJP3FHqRaRESqRESqREConMaU4VkpZva+wBafkGzB6QkkgkEolEIpFIpH9SfwDyhXixb11+iQAAAABJRU5ErkJggg==" class="internal" /></td><td></td></tr></tbody></table>

We won't go over this in detail, since it's actually surprisingly simple. The most important things to note are the use of the `fillStyle` property on the drawing context, and the use of a utility function (in this case `roundedRect()`). Using utility functions for bits of drawing you do often can be very helpful and reduce the amount of code you need, as well as its complexity.

We'll take another look at `fillStyle`, in more detail, later in this tutorial. Here, all we're doing is using it to change the fill color for paths from the default color of black to white, and then back again.

## Path2D objects

As we have seen in the last example, there can be a series of paths and drawing commands to draw objects onto your canvas. To simplify the code and to improve performance, the [`Path2D`](../../path2d) object, available in recent versions of browsers, lets you cache or record these drawing commands. You are able to play back your paths quickly.  
Let's see how we can construct a `Path2D` object:

[`Path2D()`](../../path2d/path2d)  
The `Path2D()` constructor returns a newly instantiated `Path2D` object, optionally with another path as an argument (creates a copy), or optionally with a string consisting of [SVG path](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths) data.

<!-- -->

    new Path2D();     // empty path object
    new Path2D(path); // copy from another Path2D object
    new Path2D(d);    // path from SVG path data

All [path methods](../../canvasrenderingcontext2d#paths) like `moveTo`, `rect`, `arc` or `quadraticCurveTo`, etc., which we got to know above, are available on `Path2D` objects.

The `Path2D` API also adds a way to combine paths using the `addPath` method. This can be useful when you want to build objects from several components, for example.

[`Path2D.addPath(path [, transform])`](../../path2d/addpath)  
Adds a path to the current path with an optional transformation matrix.

### Path2D example

In this example, we are creating a rectangle and a circle. Both are stored as a `Path2D` object, so that they are available for later usage. With the new `Path2D` API, several methods got updated to optionally accept a `Path2D` object to use instead of the current path. Here, `stroke` and `fill` are used with a path argument to draw both objects onto the canvas, for example.

    function draw() {
      var canvas = document.getElementById('canvas');
      if (canvas.getContext) {
        var ctx = canvas.getContext('2d');

        var rectangle = new Path2D();
        rectangle.rect(10, 10, 50, 50);

        var circle = new Path2D();
        circle.arc(100, 35, 25, 0, 2 * Math.PI);

        ctx.stroke(rectangle);
        ctx.fill(circle);
      }
    }

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAIUAAABwCAMAAAAHW0OkAAAAGXRFWHRTb2Z0d2FyZQBnbm9tZS1zY3JlZW5zaG907wO/PgAAAFpQTFRFAAAAFxcXODg44eHheHh4d3d37u7u////iIiIh4eHnJycTExM9fX1CgoKEBAQfX19aWlpPz8/XV1dVlZW2dnZIiIicXFx/Pz8urq6zs7OkJCQra2tx8fHKioqVaqrPQAAAXdJREFUaN7t2dluwyAQBdAxTmmCN7yT7f9/s+lbK8WBkTxkWt37buvYGAwz9KkhBAUUUEABBRRQQAEFFFBA8W5F+ODmEPZXHKojM/0pdvPJ+b5oHyl678okxYn7AJErpm6mX7l3ZW7FuaInGaacinKkjXibTeEa2kx7zaOoB3oZv2ZQWEORVLW4wt4pGlMLK2pDCalWWcVISelEFY4SEwQVZZOqKKycYqTkLGKKGzFSSikqjsILKc7EipVRLDzFRUSxFjxFL6JgDsjPIdlRceEqrhKKgavoJBSGqxglFAVXYSQUDVcxSyi4CGr/r0LHiOj4OnXMVB2rlo4VXMffTMefnbvLcTKKiYVohHZ8Ona/Sk4COk5FSk6IOk7LSioHSqooOipKSqpr8UrjkqPS+D1T2hdTNGSrQNvN17Hkq0ArqcY/7UzMKZ2JntsrMmldmsei3iR3acKRndv+Hau3BgoooIACCiiggAIKKKCAAgoooIACir+j+AL3u2fpQoUkUAAAAABJRU5ErkJggg==" class="internal" /></td><td></td></tr></tbody></table>

### Using SVG paths

Another powerful feature of the new canvas `Path2D` API is using [SVG path data](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Paths) to initialize paths on your canvas. This might allow you to pass around path data and re-use them in both, SVG and canvas.

The path will move to point (`M10 10`) and then move horizontally 80 points to the right (`h 80`), then 80 points down (`v 80`), then 80 points to the left (`h -80`), and then back to the start (`z`). You can see this example on the [`Path2D` constructor](../../path2d/path2d#using_svg_paths) page.

    var p = new Path2D('M10 10 h 80 v 80 h -80 Z');

- <a href="basic_usage" class="button minimal">« Previous</a>
- <a href="applying_styles_and_colors" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Drawing_shapes</a>
