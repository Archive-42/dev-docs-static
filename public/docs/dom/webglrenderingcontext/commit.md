WebGLRenderingContext.commit()
==============================

The `WebGLRenderingContext``.commit()` method pushes frames back to the original [`HTMLCanvasElement`](../htmlcanvaselement), if the context is not directly fixed to a specific canvas.

Syntax
------

    void WebGLRenderingContext.commit()

Examples
--------

    var htmlCanvas = document.createElement('canvas');
    var offscreen = htmlCanvas.transferControlToOffscreen();
    var gl = offscreen.getContext('webgl');

    // ... some drawing using the gl context ...

    // Push frames back to the original HTMLCanvasElement
    gl.commit();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#offscreencontext-commit">HTML Living Standard<br />
<span class="small">The definition of 'the commit() method of the OffscreenCanvas object's rendering context' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`commit`

No

No

44

No

No

No

No

No

No

No

No

No

See also
--------

-   The interface defining this method, [`WebGLRenderingContext`](../webglrenderingcontext)
-   [`OffscreenCanvas`](../offscreencanvas)
-   [`HTMLCanvasElement.transferControlToOffscreen()`](../htmlcanvaselement/transfercontroltooffscreen)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/commit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLRenderingContext/commit</a>
