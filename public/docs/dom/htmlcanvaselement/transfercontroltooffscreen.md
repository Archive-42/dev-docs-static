# HTMLCanvasElement.transferControlToOffscreen()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The ` HTMLCanvasElement``.transferControlToOffscreen() ` method transfers control to an [`OffscreenCanvas`](../offscreencanvas) object, either on the main thread or on a worker.

## Syntax

    OffscreenCanvas HTMLCanvasElement.transferControlToOffscreen()

### Return value

An [`OffscreenCanvas`](../offscreencanvas) object.

## Examples

    var htmlCanvas = document.createElement('canvas');
    var offscreen = htmlCanvas.transferControlToOffscreen();
    var gl = offscreen.getContext('webgl');

    // ... some drawing using the gl context ...

    // Push frames back to the original HTMLCanvasElement
    gl.commit();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/canvas.html#dom-canvas-transfercontroltooffscreen">HTML Living Standard<br />
<span class="small">The definition of 'HTMLCanvasElement.transferControlToOffscreen()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`transferControlToOffscreen`

69

79

44

No

56

No

No

69

44

48

No

10.0

## See also

- The interface defining this method, [`HTMLCanvasElement`](../htmlcanvaselement)
- [`OffscreenCanvas`](../offscreencanvas)
- [`WebGLRenderingContext.commit()`](../webglrenderingcontext/commit)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/transferControlToOffscreen" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/transferControlToOffscreen</a>
