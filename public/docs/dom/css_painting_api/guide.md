# Using the CSS Painting API

The CSS Paint API is designed to enable developers to programmatically define images which can then be used anywhere a CSS image can be invoked, such as CSS `background-image`, `border-image`, `mask-image`, etc.

To programmatically create an image used by a CSS stylesheet we need to work through a few steps:

1.  Define a paint worklet using the `registerPaint()` function
2.  Register the worklet
3.  Include the `paint()` CSS function

To elaborate over these steps, we're going to start by creating a half-highlight background, like on this header:

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAO8AAAA2CAMAAAAYnz5sAAAAV1BMVEUpKSnGxsZhXh7v5gHd1AWXkRPm5ub16wD///+/twvp4AKspg/PxgiZmZnWzQajnRG2rw2JhBbHvwnt7e13dBl4dBl7e3vZ2dn5+flmZmaoqKiNjY2zs7Nm7/CxAAAACXBIWXMAAAsSAAALEgHS3X78AAAAHHRFWHRTb2Z0d2FyZQBBZG9iZSBGaXJld29ya3MgQ1M1cbXjNgAABOBJREFUaN7tmemWpCoMgF1AG9RSsay13/85L4SExbJs7Zlzz8w0/GnREPKRBejKPn5WyxJv4k28iTfxJt7Em3gTb+JNvIn3T+CtctOq36Rtyr+hzvJWpk1L69ZeriB87p4zz0zLF1O4WeLe16uXLdXt5oWB91v05Qovu63Bt/xi58zu+fQdXhyNs1Av/394FyMvX/JOz8y3+3VHBFbVb+S96VB4fo+3655LB4N7u25D23Q3IpdHnndg5m3XfJGBdl6apesu0LvuN7/7Hi8GRx5ryjaL2c0Y95wwsPVzdZzXzhsH/CHzf403cLBNjq+S8dP1tJ+ufw1vXdcM+ERNjUO/ft+k/jz6bhMO3mjZQo5Fs4jtOV8bj9Qd5i3KwAyYm9vW1q19GEi30p9ZaGlhJ1b9nGV8cJ/YoG2ae3WUt9V65v4U9LJCm0HDei05D6XnNRKXx9XWAd3y6ZFlj2qLt/C2cOLFkinAFN04zThG7qVW4sCsQNPaAl/w8ghv2eCw3gyTM5Xu3soNNMuM6pz844Z1/gLV9LnFK5yDTa/f5tXPwytu4TcoQQBkW3mAF5atIEKItgK64PBTsA9adV7+4fe1tQoU8pbOwZqV49zm5UCLOkbp+5qwZt0HqQ0qLJ/Uf8/aRNmQ+Bpv3CAqUKyxSSOsn9kZ11v/zZSs5UC8KP/xiduEqYL3yRwhpg3emhxsYBit9UCu0ba3kZ1srYYJ97kBezFiTLTI3bxnGG2zpgcTFJoyo3uVW1/h5WGbeCCvTuXH6yYZ8ZKDG7OOxGsgWjuLK2dWXi15fUIYFXNIR1p28frFFKBG8DOjOLZrd8b8sepIHja0i9/lqvy66V80GNwb5dJoZ2mCTF2L58bnN5gmgyAYrfyu/DWD7XYw02ephBCN7Y1eh30keXtAe9nV3/NaB1uzHe8JrC4XAVwEtSvYDYcw3qEo+G98L69YOrydw14W7SNiKX+AFxzMXJFASyA72sX+QwlJqcsYzN4seaW3rP8W7znuWx0q8m8kfznCaxyMnvO85qkcw2pFW9bifBXEs1rGc3Ewnus4d3rm35+dDswqkn9zSt3gxaViEa/R2kTVijYFvwIjpbysg6TPnMMZ7p27eEnY6J176fAH+8Ddsipfr06W93l5TEd44cTAF2c7e3hZHC+YO/7gvsrAn9bnrY25hhxswuNc7j5vuOLAzDLTW1b4cFfuhfDyAGouPV/x2tInBKat/tMKTm9o05CL6tTCmYaLVokmsGRsGWvwMgGrNzAG9eZkktx4nLm6R/O22KM5jUfHE2OiMAECg6RUcH4qpQStjf1q1aF8ld/NnW2q4HpaVbd3vMHZTCvj/gCNzhizlWpsgcO6Am6k4yNbiDRBXQkOpcEpNbCCe7WlP6UWmGzKz0LXGl+ubvbqnq3fyF946xP4NOZts0W1wqIcmGU/l3SS5xgN5gwIhqn6CK8T5YziVnuQcSwupwIvJe7aSvLd9LGDV2DzG2wbvdG8xfotWMElUZx8QoqG90G/1JnBByXtN2w+nm1rox7MKbUePuAilwrupPoaxLkq3VeJZpJ8l8N98Jpjm97Xqy+v1UP957cD9/3NJtcuB/8wr1q92/+9vJtNZ4M+hWNq/IDfj7rof+KJ91/jnY79ipV+D028iTfxJt7Em3gT7w/n/Q9jPGYIJHrA3QAAAABJRU5ErkJggg==" alt="Text reading &#39;My Cool Header&#39; with a solid yellow background image block on the bottom left two thirds of the header" width="239" height="54" />

## CSS paint worklet

In an external script file, we employ the `registerPaint()` function to name our [CSS Paint worklet](../paintworklet). It takes two parameters. The first is the name we give the worklet — this is the name we will use in our CSS as the parameter of the `paint()` function when we want to apply this styling to an element. The second parameter is the class that does all the magic, defining the context options and what to paint to the two-dimensional canvas that will be our image.

    registerPaint('headerHighlight', class {

      /*
           define if alphatransparency  is allowed alpha
           is set to true by default. If set to false, all
           colors used on the canvas will be fully opaque
        */
      static get contextOptions() {
               return { alpha: true };
        }

        /*
            ctx is the 2D drawing context
            a subset of the HTML5 Canvas API.
        */
      paint(ctx) {
            ctx.fillStyle = 'hsla(55, 90%, 60%, 1.0)';
            ctx.fillRect(0, 15, 200, 20);     /* order: x, y, w, h */
      }
    });

In this class example we have defined a single context option with the `contextOptions()` function: we returned a simple object stating alpha transparency is allowed.

We have then used the `paint()` function to paint to our canvas.

A `paint()` function can take three arguments. Here we have provided one argument: the rendering context (we'll look at more in due course), often referred to by the variable name `ctx`. The 2D Rendering Context is a subset of the [HTML5 Canvas API](../canvas_api); the version available to Houdini (called the `PaintRenderingContext2D`) is a further subset containing most of the features available in the full Canvas API with the [exception](https://drafts.css-houdini.org/css-paint-api-1/#2d-rendering-context)) of the `CanvasImageData`, `CanvasUserInterface`, `CanvasText`, and `CanvasTextDrawingStyles` APIs.

We define the `fillStyle` as being `hsla(55, 90%, 60%, 1.0)`, which is a shade of yellow, and then call `fillRect()` to create a rectangle of that color. The `fillRect()` parameters are, in order, x-axis origin, y-axis origin, width, and height. `fillRect(0, 15, 200, 20)` results in the creation of a rectangle that is 200 units wide by 20 units tall, positioned 0 units from the left and 15 units from the top of the content box.

We can use the CSS `background-size` and `background-position` properties to re-size or relocate this background image, but this is the default size and placement of the yellow box we created in our paint worklet.

We tried to keep the example simple. For more options, look at the [canvas documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas). We also add a little bit of complexity later in this tutorial.

## Using the paint worklet

To use the paint worklet, we need to register it using `addModule()` and include it in our CSS, ensuring the CSS selector matches a DOM node in our HTML

### Registering the worklet

The setup and design of our paint worklet took place in the external script shown above. We need to register that [worklet](../paintworklet) from our main script.

    CSS.paintWorklet.addModule('nameOfPaintWorkletFile.js');

This can be done using the paint worklet's `addModule()` method in a `<script>` within the main HTML or in an external JavaScript file linked to from the document.

In our example, the paintworklet is stored on Github.

    CSS.paintWorklet.addModule('https://mdn.github.io/houdini-examples/cssPaint/intro/01partOne/header-highlight.js');

### Reference the paint worklet in CSS

Once we have a registered paint worklet, we can use it in CSS. Employ the CSS `paint()` function like we would any other `<image>` type, using the same string identifier we used in the paintworklet's `registerPaint()` function.

    .fancy {
      background-image: paint(headerHighlight);
    }

### Putting it together

We can then add the fancy class to any element on the page to add a yellow box as a background:

    <h1 class="fancy">My Cool Header</h1>

The following example will look like the image above in [browsers supporting the CSS Painting API](../css/paintworklet#browser_compatibility).

While you can't play with the worklet's script, you can alter the `background-size` and `background-position` to change the size and location of the background image.

## PaintSize

In the example above, we created a 20x200 unit box, painted 15 units from the top of the element it is the same regardless of the size of the element. If the text is small, the yellow box looks like a huge underline. If the text is huge, the box might look like an bar above the first three letters. It would be better if the background image was relative to the size of the element — we can use the element's `paintSize` property to ensure the background image is proportional to the size of the element's box model size.

<img src="data:image/png;base64,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" alt="The background is 50% of the height and 60% of the width of the element" width="554" height="148" />

In the above image, the background proportional to the size of the element. The 3rd example has `width: 50%`; set on the block level element, making the element narrower and therefore the background image narrower.

The code to do this looks like so:

    registerPaint('headerHighlight', class {

      static get contextOptions() {
               return { alpha: true };
      }

        /*
            ctx is the 2D drawing context
            size is the paintSize, the dimensions (height and width) of the box being painted
        */

      paint(ctx, size) {
            ctx.fillStyle = 'hsla(55, 90%, 60%, 1.0)';
            ctx.fillRect( 0, size.height / 3, size.width * 0.4, size.height * 0.6 );
      }
    });

This code example has two differences from our first example:

1.  We've included a second argument, which is the paint size.
2.  We've changed the dimensions and positioning of our rectangle to be relative to the size of the element box rather than absolute values.

We can pass the second parameter into the `paint()` function to give us access to the width and the height of the element, via `.width` and `.height` properties.

Our header now has a highlight that changes according to it's size.

While you can't play with the worklet's script, you can alter the element's `font-size` and `width` to change the size of the background image.

In browsers that support the CSS Paint API, the example below should appear like the image above.

## Custom properties

In addition to accessing the size of the element, the worklet can also have access to CSS custom properties and regular CSS properties.

    registerPaint('cssPaintFunctionName', class {
         static get inputProperties() { return ['PropertyName1', '--customPropertyName2']; }
         static get inputArguments() { return ['<color>']; }
         static get contextOptions() { return {alpha: true}; }

         paint(drawingContext, elementSize, styleMap) {
             // Paint code goes here.
         }
    });

The three parameters of the `paint()` function include the drawing context, paint size and properties. To be able to access properties, we include the static `inputProperties()` method, which provides live access to CSS properties, including regular properties and [custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Variables), and returns an `array` of property names. We'll take a look at `inputArguments` in the last section.

### Example

Let's create a list of items with a background image that rotates between three different colors and three widths.

<img src="data:image/png;base64,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" alt="The width and color of the background image changes based on the custom properties" width="739" height="255" />

In our CSS, we provide a different color and a width subtractor for the background box we've created via the `--boxColor` and `--widthSubtractor` custom properties.

    li {
       background-image: paint(boxbg);
       --boxColor: hsla(55, 90%, 60%, 1.0);
    }

    li:nth-of-type(3n) {
       --boxColor: hsla(155, 90%, 60%, 1.0);
       --widthSubtractor: 20;
    }

    li:nth-of-type(3n+1) {
       --boxColor: hsla(255, 90%, 60%, 1.0);
       --widthSubtractor: 40;
    }

In our worklet, we can reference those custom properties.

    registerPaint('boxbg', class {

      static get contextOptions() { return {alpha: true}; }

      /*
         use this function to retrieve any custom properties (or regular properties, such as 'height')
         defined for the element, return them in the specified array
      */
      static get inputProperties() { return ['--boxColor', '--widthSubtractor']; }

      paint(ctx, size, props) {
        /*
           ctx -> drawing context
           size -> paintSize: width and height
           props -> properties: get() method
        */

        ctx.fillStyle = props.get('--boxColor');
        ctx.fillRect(0, size.height/3, size.width*0.4 - props.get('--widthSubtractor'), size.height*0.6);
      }
    });

We used the `inputProperties()` method in the `registerPaint()` class to get the values of two custom properties set on an element that has `boxbg` applied to it and then used those within our `paint()` function. The `inputProperties()` method can return all properties affecting the element, not just custom properties.

In our `<script>` we register the worklet:

    CSS.paintWorklet.addModule('https://mdn.github.io/houdini-examples/cssPaint/intro/worklet/boxbg.js');

While you can't play with the worklet's script, you can alter the custom property values to change the colors and width of the background image.

## Adding complexity

The above examples might not seem very exciting, as you could recreate them in a few different ways with existing CSS properties, e.g. by positioning some decorative [generated content](https://developer.mozilla.org/en-US/docs/Learn/CSS/Howto/Generated_content) with `::before,` or including `background: linear-gradient(yellow, yellow) 0 15px / 200px 20px no-repeat;` What makes the CSS Painting API so interesting and powerful is that you can create complex images, passing variables, that automatically resize.

Let's take a look at a more complex paint example.

    registerPaint('headerHighlight', class {
      static get inputProperties() { return ['--highColour']; }
      static get contextOptions() { return {alpha: true}; }

      paint(ctx, size, props) {

            /* set where to start the highlight & dimensions */
            const x = 0;
            const y = size.height * 0.3;
            const blockWidth = size.width * 0.33;
            const highlightHeight = size.height * 0.85;
            const color = props.get('--highColour');

            ctx.fillStyle = color;

            ctx.beginPath();
            ctx.moveTo( x, y );
            ctx.lineTo( blockWidth, y );
            ctx.lineTo( blockWidth + highlightHeight, highlightHeight );
            ctx.lineTo( x, highlightHeight );
            ctx.lineTo( x, y );
            ctx.closePath();
            ctx.fill();

            /* create the dashes */
            for (let i = 0; i < 4; i++) {
                let start = i * 2;
                ctx.beginPath();
                ctx.moveTo( (blockWidth) + (start * 10) + 10, y );
                ctx.lineTo( (blockWidth) + (start * 10) + 20, y );
                ctx.lineTo( (blockWidth) + (start * 10) + 20 + (highlightHeight), highlightHeight );
                ctx.lineTo( (blockWidth) + (start * 10) + 10 + (highlightHeight), highlightHeight );
                ctx.lineTo( (blockWidth) + (start * 10) + 10, y );
                ctx.closePath();
                ctx.fill();
            }
      } // paint
    });

We can then create a little HTML that will accept this image as backgrounds:

    <h1 class="fancy">Largest Header</h1>
    <h3 class="fancy">Medium size header</h3>
    <h6 class="fancy">Smallest Header</h6>

We give each header a different value for the `--highColour` [custom property](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Variables)

    .fancy {
      background-image: paint(headerHighlight);
    }
    h1 { --highColour: hsla(155, 90%, 60%, 0.7); }
    h3 { --highColour: hsla(255, 90%, 60%, 0.5); }
    h6 { --highColour: hsla(355, 90%, 60%, 0.3); }

And we register our worklet

    CSS.paintWorklet.addModule('https://mdn.github.io/houdini-examples/cssPaint/intro/03partThree/header-highlight.js');

While you can't edit the worklet itself, you can play around with the CSS and HTML. Maybe try `float` and `clear` on the headers?

You could try making the background images above without the CSS paint API. It is doable, but you would have to declare a different, fairly complex linear gradient for each different color you wanted to create. With the CSS Paint API, one worklet can be re-used, with different colors passed in this case.

## Passing parameters

With the CSS Paint API, we not only have access to custom properties and regular properties, but we can pass custom arguments to the `paint()` function as well.

We can add these extra arguments when we call the function in the CSS. Let's say we want to sometimes stroke our background instead of fill it — let's pass in an extra argument for this occasion.

    li {
        background-image: paint(hollowHighlights, stroke);
    }

Now we can use the `inputArguments()` method in the `registerPaint()` class to access the custom argument we have added to our `paint()` function.

    static get inputArguments() { return ['*']; }

We then have access to that argument.

    paint(ctx, size, props, args) {

        // use our custom arguments
        const hasStroke = args[0].toString();

        // if stroke arg is 'stroke', don't fill
        if (hasStroke === 'stroke') {
            ctx.fillStyle = 'transparent';
            ctx.strokeStyle = color;
        }
        ...
    }

We can pass more than one argument.

    li {
        background-image: paint(hollowHighlights, stroke, 10px);
    }

We can also specify that we want a particular type of argument. When we `get` our list of argument values, we ask specifically for a `<length>` unit.

    static get inputArguments() { return ['*', '<length>']; }

In this case, we specifically requested the `<length>` attribute. The first element in the returned array will be a `CSSUnparsedValue`. The second will be a `CSSStyleValue.`

If the custom argument is a CSS value, for instance a unit, we can invoke Typed OM CSSStyleValue class (and sub classes) by using the value type keyword when we retrieve it in the `registerPaint()` function.

Let's say we add a second argument with how many pixels wide we want the stroke to be:

    li {
        background-image: paint(hollowHighlights, stroke, 10px);
    }

When we `get` our list of argument values, we can ask specifically for a `<length>` unit.

    static get inputArguments() { return ['*', '<length>']; }

Now we can access the type and value properties, meaning we can get the number of pixels and a number type right out of the box. (Admittedly, `ctx.lineWidth` takes a float as a value rather than a value with length units, but for example's sake...)

    paint(ctx, size, props, args) {

            const strokeWidth = args[1];

            if (strokeWidth.unit === 'px') {
                ctx.lineWidth = strokeWidth.value;
            } else {
                ctx.lineWidth = 1.0;
            }

        ...
    }

It's worth noting the difference between using custom properties to control different parts of this worklet and the arguments set out here. Custom properties (and in fact any properties on the style map) are global — they can be used elsewhere within our CSS (and JS).

You may for example have a `--mainColor`, which will be useful for setting the color within a `paint()` function, but can also be used to set colors elsewhere in your CSS. If you wanted to change it specifically for paint, it could prove difficult. This is where the custom argument feature comes in handy. Another way to think about it is that arguments are set to control what you are actually drawing, whereas properties are set to control styling.

<img src="data:image/png;base64,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" alt="The list items have a background image that is either pink, purple or green, with different stroke widths, and the green one being filled." width="327" height="292" />

Now we can really start to see the benefits of this API, if we can control a myriad of drawing parameters from our CSS through both custom properties and extra `paint()` function arguments, then we can really start to build reusable and highly controllable styling functions.

    registerPaint('hollowHighlights', class {

      static get inputProperties() { return ['--boxColor']; }
      // Input arguments that can be passed to the `paint` function
      static get inputArguments() { return ['*','']; }

      static get contextOptions() { return {alpha: true}; }

      paint(ctx, size, props, args) {
        // ctx   -> drawing context
        // size  -> size of the box being painted
        // props -> list of custom properties available to the element
        // args  -> list of arguments set when calling the paint() function in the css

            // where to start the highlight & dimensions
            const x = 0;
            const y = size.height * 0.3;
            const blockWidth = size.width * 0.33;
            const blockHeight = size.height * 0.85;

            // the values passed in the paint() function in the CSS
            const color = props.get( '--boxColor' );
            const strokeType = args[0].toString();
            const strokeWidth = parseInt(args[1]);

            // set the stroke width
            if ( strokeWidth ) {
                ctx.lineWidth = strokeWidth;
            } else {
                ctx.lineWidth = 1.0;
            }
            // set the fill type
            if ( strokeType === 'stroke' ) {
                ctx.fillStyle = 'transparent';
                ctx.strokeStyle = color;
            } else if ( strokeType === 'filled' ) {
                ctx.fillStyle = color;
                ctx.strokeStyle = color;
            } else {
                ctx.fillStyle = 'none';
                ctx.strokeStyle = 'none';
            }

            // block
            ctx.beginPath();
            ctx.moveTo( x, y );
            ctx.lineTo( blockWidth, y );
            ctx.lineTo( blockWidth + blockHeight, blockHeight );
            ctx.lineTo( x, blockHeight );
            ctx.lineTo( x, y );
            ctx.closePath();
            ctx.fill();
            ctx.stroke();
            // dashes
            for (let i = 0; i < 4; i++) {
                let start = i * 2;
                ctx.beginPath();
                ctx.moveTo( blockWidth + (start * 10) + 10, y);
                ctx.lineTo( blockWidth + (start * 10) + 20, y);
                ctx.lineTo( blockWidth + (start * 10) + 20 + blockHeight, blockHeight);
                ctx.lineTo( blockWidth + (start * 10) + 10 + blockHeight, blockHeight);
                ctx.lineTo( blockWidth + (start * 10) + 10, y);
                ctx.closePath();
                ctx.fill();
                ctx.stroke();
            }

      } // paint
    });

We can set different colors, stroke widths, and pick whether the background image should be filled or hollow:

    li {
       --boxColor: hsla(155, 90%, 60%, 0.5);
       background-image: paint(hollowHighlights, stroke, 5px);
    }

    li:nth-of-type(3n) {
       --boxColor: hsla(255, 90%, 60%, 0.5);
       background-image: paint(hollowHighlights, filled,  3px);
    }

    li:nth-of-type(3n+1) {
       --boxColor: hsla(355, 90%, 60%, 0.5);
       background-image: paint(hollowHighlights, stroke, 1px);
    }

In our `<script>` we register the worklet:

    CSS.paintWorklet.addModule('https://mdn.github.io/houdini-examples/cssPaint/intro/worklets/hollow.js');

## See also

- [CSS Painting API](../css_painting_api)
- [CSS Typed Object Model API](../css_typed_om_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS_Painting_API/Guide" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSS_Painting_API/Guide</a>
