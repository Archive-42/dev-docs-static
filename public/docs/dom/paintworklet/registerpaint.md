# PaintWorkletGlobalScope.registerPaint

**Draft**

This page is not complete.

The `PaintWorkletGlobalScope.registerPaint()` method of the [`PaintWorklet`](../paintworklet) interface registers a class programmatically generate an image where a CSS property expects a file.

## Syntax

    registerPaint(name, class);

### Parameters

name  
The name of the worklet class to register.

class  
A reference to the class that implements the worklet.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined)

### Exceptions

TypeError  
Thrown when one of the arguments is invalid or missing.

InvalidModificationError  
Thrown when the a worklet already exists with the specified name.

## Examples

The following shows registering an example worklet module. This should be in a separate js file. Note that `registerPaint()` is called without a reference to `PaintWorkletGlobalScope`. The file itself is loaded through `CSS.paintWorklet.addModule()` (documented here on the parent class of PaintWorklet, at [`Worklet.addModule()`](../worklet/addmodule).

    /* checkboardWorklet.js */

    class CheckerboardPainter {
      paint(ctx, geom, properties) {
        // Use `ctx` as if it was a normal canvas
        const colors = ['red', 'green', 'blue'];
        const size = 32;
        for(let y = 0; y < geom.height/size; y++) {
          for(let x = 0; x < geom.width/size; x++) {
            const color = colors[(x + y) % colors.length];
            ctx.beginPath();
            ctx.fillStyle = color;
            ctx.rect(x * size, y * size, size, size);
            ctx.fill();
          }
        }
      }
    }

    // Register our class under a specific name
    registerPaint('checkerboard', CheckerboardPainter);

The first step in using a paintworket is defining the paint worklet using the `registerPaint()` function, as done above. To use it, you register it with the `CSS.paintWorklet.addModule()` method:

    <script>
       CSS.paintWorklet.addModule('checkboardWorklet.js');
    </script>

You can then use the `paint()` CSS function in your CSS anywhere an `<image>` value is valid.

    li {
       background-image: paint(checkerboard);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-paint-api-1/#dom-paintworkletglobalscope-registerpaint">CSS Painting API Level 1<br />
<span class="small">The definition of 'PaintWorkletGlobalScope.registerPaint' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`registerPaint`

65

≤79

No

No

?

No

65

65

No

?

No

9.0

## See also

- [CSS Painting API](../css_painting_api)
- [Houdini APIs](https://developer.mozilla.org/en-US/docs/Web/Houdini)
- [Houdini overview](https://developer.mozilla.org/en-US/docs/Web/Houdini/learn)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaintWorklet/registerPaint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaintWorklet/registerPaint</a>
