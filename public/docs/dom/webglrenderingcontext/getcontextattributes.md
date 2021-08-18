WebGLRenderingContext.getContextAttributes()
============================================

The `WebGLRenderingContext.getContextAttributes()` method returns a `WebGLContextAttributes` object that contains the actual context parameters. Might return [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null), if the context is lost.

Syntax
------

    gl.getContextAttributes();

### Return value

A `WebGLContextAttributes` object that contains the actual context parameters, or [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) if the context is lost.

Examples
--------

Given this [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element

    <canvas id="canvas"></canvas>

and given this WebGL context

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');
    gl.getContextAttributes();

the `getContextAttributes` method returns an object that describes the attributes set on this context, for example:

    {
      alpha: true,
      antialias: true,
      depth: true,
      failIfMajorPerformanceCaveat: false,
      powerPreference: "default",
      premultipliedAlpha: true,
      preserveDrawingBuffer: false,
      stencil: false,
      desynchronized: false
    }

The context attributes can be set when creating the context using the [`HTMLCanvasElement.getContext()`](../htmlcanvaselement/getcontext) method:

    canvas.getContext('webgl',
                     { antialias: false,
                       depth: false });

See [`getContext()`](../htmlcanvaselement/getcontext) for more information about the individual attributes.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.14.2">WebGL 1.0<br />
<span class="small">The definition of 'WebGLRenderingContext.getContextAttributes' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getContextAttributes`

9

12

4

11

12

5.1

≤37

25

Yes

12

8

1.5

See also
--------

-   [`HTMLCanvasElement.getContext()`](../htmlcanvaselement/getcontext)
-   [`CanvasRenderingContext2D.getContextAttributes()`](../canvasrenderingcontext2d/getcontextattributes)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getContextAttributes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/getContextAttributes</a>
