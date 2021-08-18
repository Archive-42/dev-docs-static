PaintWorklet
============

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `PaintWorklet` interface of the [CSS Painting API](css_painting_api) programmatically generates an image where a CSS property expects a file. Access this interface through [`CSS.paintWorklet`](css/paintworklet).

Properties
----------

[`PaintWorklet.devicePixelRatio`](paintworklet/devicepixelratio)  
Returns the current device's ratio of physical pixels to logical pixels.

### Event handlers

None.

Methods
-------

*This interface inherits methods from [`Worklet`](worklet).*

[`PaintWorklet.registerPaint()`](paintworklet/registerpaint)  
Registers a class programmatically generate an image where a CSS property expects a file.

[`CSS.PaintWorklet.addModule()`](worklet/addmodule)  
The `addModule()` method, inhertied from the *[`Worklet`](worklet)* interface loads the module in the given JavaScript file and adds it to the current PaintWorklet.

Examples
--------

The following three examples go together to show creating, loading, and using a `PaintWorklet`.

### Create a PaintWorklet

The following shows an example worklet module. This should be in a separate js file. Note that `registerPaint()` is called without a reference to `PaintWorklet`.

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

### Load a PaintWorklet

The following example demonstrates loading the above worklet from its js file and does so by feature detection.

    <script>
      if ('paintWorklet' in CSS) {
        CSS.paintWorklet.addModule('checkerboard.js');
      }
    </script>

### Use a PaintWorklet

This example shows how to use a `PaintWorklet` in a stylesheet, including the simplest way to provide a fallback if `PaintWorklet` isn't supported.

    <style>
      textarea {
        background-image: url(checkerboard);
        background-image: paint(checkerboard);
      }
    </style>
    <textarea></textarea>

You can also use the [`@supports`](https://developer.mozilla.org/en-US/docs/Web/CSS/@supports) at-rule.

    @supports (background: paint(id)) {
      background-image: paint(checkerboard);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-paint-api-1/#paintworkletglobalscope">CSS Painting API Level 1<br />
<span class="small">The definition of 'PaintWorkletGlobalScope' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`PaintWorklet`

65

≤79

No

No

?

?

65

65

No

?

?

9.0

`devicePixelRatio`

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

See also
--------

-   [CSS Painting API](css_painting_api)
-   [Houdini APIs](https://developer.mozilla.org/en-US/docs/Web/Houdini)
-   [Houdini overview](https://developer.mozilla.org/en-US/docs/Web/Houdini/learn)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaintWorklet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaintWorklet</a>
