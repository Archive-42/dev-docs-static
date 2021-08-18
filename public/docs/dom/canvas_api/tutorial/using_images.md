# Using images

- <a href="drawing_text" class="button minimal">« Previous</a>
- <a href="transformations" class="button minimal">Next »</a>

Until now we have created our own [shapes](drawing_shapes) and [applied styles](applying_styles_and_colors) to them. One of the more exciting features of [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) is the ability to use images. These can be used to do dynamic photo compositing or as backdrops of graphs, for sprites in games, and so forth. External images can be used in any format supported by the browser, such as PNG, GIF, or JPEG. You can even use the image produced by other canvas elements on the same page as the source!

Importing images into a canvas is basically a two step process:

1.  Get a reference to an [`HTMLImageElement`](../../htmlimageelement) object or to another canvas element as a source. It is also possible to use images by providing a URL.
2.  Draw the image on the canvas using the `drawImage()` function.

Let's take a look at how to do this.

## Getting images to draw

The canvas API is able to use any of the following data types as an image source:

[`HTMLImageElement`](../../htmlimageelement)  
These are images created using the `Image()` constructor, as well as any [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element.

[`SVGImageElement`](../../svgimageelement)  
These are images embedded using the [`<image>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/image) element.

[`HTMLVideoElement`](../../htmlvideoelement)  
Using an HTML [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element as your image source grabs the current frame from the video and uses it as an image.

[`HTMLCanvasElement`](../../htmlcanvaselement)  
You can use another [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element as your image source.

These sources are collectively referred to by the type [`CanvasImageSource`](../../canvasimagesource).

There are several ways to get images for use on a canvas.

### Using images from the same page

We can obtain a reference to images on the same page as the canvas by using one of:

- The [`document.images`](../../document/images) collection
- The [`document.getElementsByTagName()`](../../document/getelementsbytagname) method
- If you know the ID of the specific image you wish to use, you can use [`document.getElementById()`](../../document/getelementbyid) to retrieve that specific image

### Using images from other domains

Using the [`crossorigin`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-crossorigin) attribute of an [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element (reflected by the [`HTMLImageElement.crossOrigin`](../../htmlimageelement/crossorigin) property), you can request permission to load an image from another domain for use in your call to `drawImage()`. If the hosting domain permits cross-domain access to the image, the image can be used in your canvas without tainting it; otherwise using the image will [taint the canvas](https://developer.mozilla.org/en-US/docs/Web/HTML/CORS_enabled_image#what_is_a_.22tainted.22_canvas.3f).

### Using other canvas elements

Just as with normal images, we access other canvas elements using either the [`document.getElementsByTagName()`](../../document/getelementsbytagname) or [`document.getElementById()`](../../document/getelementbyid) method. Be sure you've drawn something to the source canvas before using it in your target canvas.

One of the more practical uses of this would be to use a second canvas element as a thumbnail view of the other larger canvas.

### Creating an image from scratch

Another option is to create new [`HTMLImageElement`](../../htmlimageelement) objects in our script. To do this, you can use the convenient `Image()` constructor:

    var img = new Image();   // Create new img element
    img.src = 'myImage.png'; // Set source path

When this script gets executed, the image starts loading.

If you try to call `drawImage()` before the image has finished loading, it won't do anything (or, in older browsers, may even throw an exception). So you need to be sure to use the load event so you don't try this before the image has loaded:

    var img = new Image();   // Create new img element
    img.addEventListener('load', function() {
      // execute drawImage statements here
    }, false);
    img.src = 'myImage.png'; // Set source path

If you're only using one external image this can be a good approach, but once you need to track more than one we need to resort to something more clever. It's beyond the scope of this tutorial to look at image pre-loading tactics, but you should keep that in mind.

### Embedding an image via data: URL

Another possible way to include images is via the [data: url](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/Data_URIs). Data URLs allow you to completely define an image as a Base64 encoded string of characters directly in your code.

    var img = new Image();   // Create new img element
    img.src = 'data:image/gif;base64,R0lGODlhCwALAIAAAAAA3pn/ZiH5BAEAAAEALAAAAAALAAsAAAIUhA+hkcuO4lmNVindo7qyrIXiGBYAOw==';

One advantage of data URLs is that the resulting image is available immediately without another round trip to the server. Another potential advantage is that it is also possible to encapsulate in one file all of your [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS), [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript), [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML), and images, making it more portable to other locations.

Some disadvantages of this method are that your image is not cached, and for larger images the encoded url can become quite long.

### Using frames from a video

You can also use frames from a video being presented by a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element (even if the video is not visible). For example, if you have a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element with the ID "myvideo", you can do this:

    function getMyVideo() {
      var canvas = document.getElementById('canvas');
      if (canvas.getContext) {
        var ctx = canvas.getContext('2d');

        return document.getElementById('myvideo');
      }
    }

This returns the [`HTMLVideoElement`](../../htmlvideoelement) object for the video, which, as covered earlier, is one of the objects that can be used as a `CanvasImageSource`.

## Drawing images

Once we have a reference to our source image object we can use the `drawImage()` method to render it to the canvas. As we will see later the `drawImage()` method is overloaded and has several variants. In its most basic form it looks like this:

[`drawImage(image, x, y)`](../../canvasrenderingcontext2d/drawimage)  
Draws the `CanvasImageSource` specified by the `image` parameter at the coordinates (`x`, `y`).

SVG images must specify a width and height in the root &lt;svg&gt; element.

### Example: A simple line graph

In the following example, we will use an external image as the backdrop for a small line graph. Using backdrops can make your script considerably smaller because we can avoid the need for code to generate the background. In this example, we're only using one image, so I use the image object's `load` event handler to execute the drawing statements. The `drawImage()` method places the backdrop at the coordinate (0, 0), which is the top-left corner of the canvas.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');
      var img = new Image();
      img.onload = function() {
        ctx.drawImage(img, 0, 0);
        ctx.beginPath();
        ctx.moveTo(30, 96);
        ctx.lineTo(70, 66);
        ctx.lineTo(103, 76);
        ctx.lineTo(170, 15);
        ctx.stroke();
      };
      img.src = 'https://mdn.mozillademos.org/files/5395/backdrop.png';
    }

The resulting graph looks like this:

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAMgAAACWCAMAAACsAjcrAAAAGXRFWHRTb2Z0d2FyZQBBZG9iZSBJbWFnZVJlYWR5ccllPAAAAGBQTFRF9fX1+fn5+/v79vb2/v7++Pj4/f399/f3+vr6/Pz8////y8vL5eXlQkJC6Ojo6urq6enpOzs7e3t7urq6GBgYKysrioqK3d3dW1tbqamp19fXmpqa8fHxa2trTExMxsbG6I6yKgAABQ5JREFUeNrt3YuSojgUBmACEwnLzdyAAOL7v+WeMGqvrUjwRsLmnxrtUeyZr/PLMVVTRfDPRhJ4iId4iId4iId4yC8ILtrUmbQFnoL0db3vA1eyr+v+PgTXWeBUshrfhRR14Fjq4i6k3bsG2bd3IWnvGiRI70MCD/EQD3kWkrsJOQpKg+BA6dFNSHROpfRNFRXy/EgeWZk5iKSsiOhZ5DCER1UzQjizEdIaQyA0gloF6gLJ7EknWkNIodsVDXB4c7RvRTpxNF0RyfjQRUfKoWDWQZhsjd8jRce4riLrItsgwUHW5m92fYb+9Q0sgfQDLZactW5jB2SfD33kPiTIZNNHG4C0kkXxBiCpqBZPdhshXKjf6+EkRAn+xGct+yB6nAfuQ2Im2iWffuPp5PGKiWCcx9G9Z9yC9A0tJp4ygBTWQEoY5/HTkGMVx3rPvj4ko00QPw+RLK6quJCrQ8Zx/jzkcGAxhftKrQyBcf7w6RkIb/hfCNytCuGii1+AFLIAAdQqUhfIGpvzohPq7hOmkGFgDeVDG8fNcc0VgXE+17yHkIxz2K234559xTd7VIk0fgkC3yNqOZwwWLfiHBnHOX4RYsFkfzDOnYKUw/Q4dwkC49zEMQXB08nxN1PDBwujA+2GIBjnhofaDTmKDm8AQpRQeAsQGOcYbQAC43zB0dZCYiZr8/WwFxI0NFv0AkshPYxz/E5IQamEP8CePf0mpIBxjt8KUQq3A64qXMgvQmp5iPF7IfqnM2CqzyHqW5CoNR7n8xB0SSdSROGes9MDOfpwYJwjvPhVsxCkGJJ/706Q4rOBcb7gaFNIB78pGlqEmvQ7KwLj/In1mIWwhjcKpXrPjr4BITDOn3vlXLU443ALe3b0DQiGcY4+A7nNByExjHO0AUg/5CXaAGQP4xxtAALjHKMNQFrBXnq9LRA9zomlEN4Zn4IwF+rFn8QEhEwnJ0aJmaCCVq3RwUpw8mI+BEFZnmek5wchDzyaOTiBcU4shXDBYu1BJGVSNKp8dDCMc2InBGr1U5UwrLtB5JMliw4yI3ZCxlpdN61XjZDsiG8P1uOcfB5S6j07IXrPbgw51eo6IcHHsWT99eNl3gTkC5CGg4VUFSmlIeSqVtfLgkhb5WLo/vOOyGCck29A9BcUfhFSKRMIuq3V9bqQ/Viy01/QSkbIVyCQrhshnJlA7tbq98JE/CDFgfckFR35GqQ7EKJrpS6Q/WQyJtTeKMWRUSFFt381xpC0gZsBWt2ksyvyuFa3h3eckE+vSHhKKhTn4bhnPz+UhxOBWuFwSZLwjZmBVAwCI4114QwEw9kqXDEzkDu5CxlrFW4AsrhWdkLWrtW7IKvX6k2Q9Wv1FogNtXoDhFhRqzdA7KjVyxBbavUqxJpaPYAk08nPX0CtUGJNnoYgqFWSuAOpxn+u3rNfQ3StEpcgCQNIVSWlvILYVStjCNVLo34gttVqEYSzC8S6WhlDdK3UBdIKVpS2ZBlkqJOkSS8r0iZh4uaKjHv2nze7hQwDCIfVSGDPfjsQHYNMT3YP8ZD/M2Q3nXxnZTzEQzzEQzzEYojes28BUlW7Um4BQne7P5XaBmTH2QYgulbqBMntyjLIUO92TbqBFRn37Du7Y3b6hT37zk3IH+fiIR7iIU9BiGuOif+v1fauQfp24pIErkEmLkmA69ItRzlxkQh92Y7emfcJ6Scv27GdC6n4a/R4iId4iId4iIe4nn8Brn3+5fjwxr0AAAAASUVORK5CYII=" class="internal" /></td><td></td></tr></tbody></table>

## Scaling

The second variant of the `drawImage()` method adds two new parameters and lets us place scaled images on the canvas.

[`drawImage(image, x, y, width, height)`](../../canvasrenderingcontext2d/drawimage)  
This adds the `width` and `height` parameters, which indicate the size to which to scale the image when drawing it onto the canvas.

### Example: Tiling an image

In this example, we'll use an image as a wallpaper and repeat it several times on the canvas. This is done by looping and placing the scaled images at different positions. In the code below, the first `for` loop iterates over the rows. The second `for` loop iterates over the columns. The image is scaled to one third of its original size, which is 50x38 pixels.

**Note**: Images can become blurry when scaling up or grainy if they're scaled down too much. Scaling is probably best not done if you've got some text in it which needs to remain legible.

    function draw() {
      var ctx = document.getElementById('canvas').getContext('2d');
      var img = new Image();
      img.onload = function() {
        for (var i = 0; i < 4; i++) {
          for (var j = 0; j < 3; j++) {
            ctx.drawImage(img, j * 50, i * 38, 50, 38);
          }
        }
      };
      img.src = 'https://mdn.mozillademos.org/files/5397/rhino.jpg';
    }

The resulting canvas looks like this:

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/png;base64,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" class="internal" /></td><td></td></tr></tbody></table>

## Slicing

The third and last variant of the `drawImage()` method has eight parameters in addition to the image source. It lets us cut out a section of the source image, then scale and draw it on our canvas.

[`drawImage(image, sx, sy, sWidth, sHeight, dx, dy, dWidth, dHeight)`](../../canvasrenderingcontext2d/drawimage)  
Given an `image`, this function takes the area of the source image specified by the rectangle whose top-left corner is (`sx`, `sy`) and whose width and height are `sWidth` and `sHeight` and draws it into the canvas, placing it on the canvas at (`dx`, `dy`) and scaling it to the size specified by `dWidth` and `dHeight`.

<img src="data:image/jpeg;base64,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" class="internal" width="300" height="290" />To really understand what this does, it may help to look at the image to the right. The first four parameters define the location and size of the slice on the source image. The last four parameters define the rectangle into which to draw the image on the destination canvas.

Slicing can be a useful tool when you want to make compositions. You could have all elements in a single image file and use this method to composite a complete drawing. For instance, if you want to make a chart you could have a PNG image containing all the necessary text in a single file and depending on your data could change the scale of your chart fairly easily. Another advantage is that you don't need to load every image individually, which can improve load performance.

### Example: Framing an image

In this example, we'll use the same rhino as in the previous example, but we'll slice out its head and composite it into a picture frame. The picture frame image is a 24-bit PNG which includes a drop shadow. Because 24-bit PNG images include a full 8-bit alpha channel, unlike GIF and 8-bit PNG images, it can be placed onto any background without worrying about a matte color.

    <html>
     <body onload="draw();">
       <canvas id="canvas" width="150" height="150"></canvas>
       <div style="display:none;">
         <img id="source" src="https://mdn.mozillademos.org/files/5397/rhino.jpg" width="300" height="227">
         <img id="frame" src="https://mdn.mozillademos.org/files/242/Canvas_picture_frame.png" width="132" height="150">
       </div>
     </body>
    </html>

    function draw() {
      var canvas = document.getElementById('canvas');
      var ctx = canvas.getContext('2d');

      // Draw slice
      ctx.drawImage(document.getElementById('source'),
                    33, 71, 104, 124, 21, 20, 87, 104);

      // Draw frame
      ctx.drawImage(document.getElementById('frame'), 0, 0);
    }

We took a different approach to loading the images this time. Instead of loading them by creating new [`HTMLImageElement`](../../htmlimageelement) objects, we included them as [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) tags directly in our HTML source and retrieved the images from those. The images are hidden from output by setting the CSS property [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) to none for those images.

<table><thead><tr class="header"><th>Screenshot</th><th>Live sample</th></tr></thead><tbody><tr class="odd"><td><img src="data:image/jpeg;base64,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" class="internal" /></td><td></td></tr></tbody></table>

The script itself is very simple. Each [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) is assigned an ID attribute, which makes them easy to select using [`document.getElementById()`](../../document/getelementbyid). We then use `drawImage()` to slice the rhino out of the first image and scale him onto the canvas, then draw the frame on top using a second `drawImage()` call.

## Art gallery example

In the final example of this chapter, we'll build a little art gallery. The gallery consists of a table containing several images. When the page is loaded, a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element is inserted for each image and a frame is drawn around it.

In this case, every image has a fixed width and height, as does the frame that's drawn around them. You could enhance the script so that it uses the image's width and height to make the frame fit perfectly around it.

The code below should be self-explanatory. We loop through the [`document.images`](../../document/images) container and add new canvas elements accordingly. Probably the only thing to note, for those not so familiar with the DOM, is the use of the [`Node.insertBefore`](../../node/insertbefore) method. `insertBefore()` is a method of the parent node (a table cell) of the element (the image) before which we want to insert our new node (the canvas element).

    <html>
     <body onload="draw();">
         <table>
          <tr>
            <td><img src="https://mdn.mozillademos.org/files/5399/gallery_1.jpg"></td>
            <td><img src="https://mdn.mozillademos.org/files/5401/gallery_2.jpg"></td>
            <td><img src="https://mdn.mozillademos.org/files/5403/gallery_3.jpg"></td>
            <td><img src="https://mdn.mozillademos.org/files/5405/gallery_4.jpg"></td>
          </tr>
          <tr>
            <td><img src="https://mdn.mozillademos.org/files/5407/gallery_5.jpg"></td>
            <td><img src="https://mdn.mozillademos.org/files/5409/gallery_6.jpg"></td>
            <td><img src="https://mdn.mozillademos.org/files/5411/gallery_7.jpg"></td>
            <td><img src="https://mdn.mozillademos.org/files/5413/gallery_8.jpg"></td>
          </tr>
         </table>
         <img id="frame" src="https://mdn.mozillademos.org/files/242/Canvas_picture_frame.png" width="132" height="150">
     </body>
    </html>

And here's some CSS to make things look nice:

    body {
      background: 0 -100px repeat-x url(https://mdn.mozillademos.org/files/5415/bg_gallery.png) #4F191A;
      margin: 10px;
    }

    img {
      display: none;
    }

    table {
      margin: 0 auto;
    }

    td {
      padding: 15px;
    }

Tying it all together is the JavaScript to draw our framed images:

    function draw() {

      // Loop through all images
      for (var i = 0; i < document.images.length; i++) {

        // Don't add a canvas for the frame image
        if (document.images[i].getAttribute('id') != 'frame') {

          // Create canvas element
          canvas = document.createElement('canvas');
          canvas.setAttribute('width', 132);
          canvas.setAttribute('height', 150);

          // Insert before the image
          document.images[i].parentNode.insertBefore(canvas,document.images[i]);

          ctx = canvas.getContext('2d');

          // Draw image to canvas
          ctx.drawImage(document.images[i], 15, 20);

          // Add frame
          ctx.drawImage(document.getElementById('frame'), 0, 0);
        }
      }
    }

## Controlling image scaling behavior

As mentioned previously, scaling images can result in fuzzy or blocky artifacts due to the scaling process. You can use the drawing context's [`imageSmoothingEnabled`](../../canvasrenderingcontext2d/imagesmoothingenabled) property to control the use of image smoothing algorithms when scaling images within your context. By default, this is `true`, meaning images will be smoothed when scaled. You can disable this feature like this:

    ctx.mozImageSmoothingEnabled = false;
    ctx.webkitImageSmoothingEnabled = false;
    ctx.msImageSmoothingEnabled = false;
    ctx.imageSmoothingEnabled = false;

- <a href="drawing_text" class="button minimal">« Previous</a>
- <a href="transformations" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Using_images" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial/Using_images</a>
