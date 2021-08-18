# CSS Painting API

The CSS Painting API — part of the [CSS Houdini](https://developer.mozilla.org/en-US/docs/Web/Houdini) umbrella of APIs — allows developers to write JavaScript functions that can draw directly into an element's background, border, or content.

## Concepts and usage

Essentially, the CSS Painting API contains functionality allowing developers to create custom values for [`paint()`](<https://developer.mozilla.org/en-US/docs/Web/CSS/paint()>), a CSS `<image>` function. You can then apply these values to properties like [`background-image`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-image) to set complex custom backgrounds on an element.

For example:

    aside {
      background-image: paint(myPaintedImage);
    }

The API defines [`PaintWorklet`](paintworklet), a [`worklet`](worklet) that can be used to programmatically generate an image that responds to computed style changes. To find out more about how this is used, consult [Using the CSS Painting API](css_painting_api/guide).

## Interfaces

[`PaintWorklet`](paintworklet)  
Programmatically generates an image where a CSS property expects a file. Access this interface through [`CSS.paintWorklet`](css/paintworklet).

<span class="page-not-created">`PaintWorkletGlobalScope`</span>  
The global execution context of the `paintWorklet`.

<span class="page-not-created">`PaintRenderingContext2D`</span>  
Implements a subset of the [CanvasRenderingContext2D API](canvasrenderingcontext2d). It has an output bitmap that is the size of the object it is rendering to.

<span class="page-not-created">`PaintSize`</span>  
Returns the read-only values of the output bitmap's width and height.

## Dictionaries

<span class="page-not-created">`PaintRenderingContext2DSettings`</span>  
A dictionary providing a subset of [CanvasRenderingContext2D](canvasrenderingcontext2d) settings.

## Examples

To draw directly into an element's background using JavaScript in our CSS, we define a paint worklet using the `registerPaint()` function, tell the document to include the worklet using the paintWorklet addModule() method, then include the image we created using the CSS `paint()` function.

We create our PaintWorklet called 'hollowHighlights' using the `registerPaint()` function:

    registerPaint('hollowHighlights', class {

      static get inputProperties() { return ['--boxColor']; }

      static get inputArguments() { return ['*','<length>']; }

      static get contextOptions() { return {alpha: true}; }

      paint(ctx, size, props, args) {
            const x = 0;
            const y = size.height * 0.3;
            const blockWidth = size.width * 0.33;
            const blockHeight = size.height * 0.85;

            const theColor = props.get( '--boxColor' );
            const strokeType = args[0].toString();
            const strokeWidth = parseInt(args[1]);

            console.log(theColor);

            if ( strokeWidth ) {
                ctx.lineWidth = strokeWidth;
            } else {
                ctx.lineWidth = 1.0;
            }

            if ( strokeType === 'stroke' ) {
                ctx.fillStyle = 'transparent';
                ctx.strokeStyle = theColor;
            } else if ( strokeType === 'filled' ) {
                ctx.fillStyle = theColor;
                ctx.strokeStyle = theColor;
            } else {
                ctx.fillStyle = 'none';
                ctx.strokeStyle = 'none';
            }

            ctx.beginPath();
            ctx.moveTo( x, y );
            ctx.lineTo( blockWidth, y );
            ctx.lineTo( blockWidth + blockHeight, blockHeight );
            ctx.lineTo( x, blockHeight );
            ctx.lineTo( x, y );
            ctx.closePath();
            ctx.fill();
            ctx.stroke();

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
      }
    });

We then include the paintWorklet:

      CSS.paintWorklet.addModule('https://mdn.github.io/houdini-examples/cssPaint/intro/worklets/hilite.js');

Then we can use the [`<image>`](https://developer.mozilla.org/en-US/docs/Web/CSS/image) with the CSS [`paint()`](<https://developer.mozilla.org/en-US/docs/Web/CSS/paint()>) function:

    li {
       --boxColor: hsla(55, 90%, 60%, 1.0);
       background-image: paint(hollowHighlights, stroke, 2px);
    }

    li:nth-of-type(3n) {
       --boxColor: hsla(155, 90%, 60%, 1.0);
       background-image: paint(hollowHighlights, filled,  3px);
    }

    li:nth-of-type(3n+1) {
       --boxColor: hsla(255, 90%, 60%, 1.0);
       background-image: paint(hollowHighlights, stroke, 1px);
    }

We've included a custom property in the selector block defining a boxColor. Custom properties are accessible to the PaintWorklet.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-paint-api-1/">CSS Painting API Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

## See also

- [Using the CSS Painting API](css_painting_api/guide)
- [CSS Typed Object Model API](css_typed_om_api)
- [CSS Houdini](https://developer.mozilla.org/en-US/docs/Web/Houdini)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS_Painting_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSS_Painting_API</a>
