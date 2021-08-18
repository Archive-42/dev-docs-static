# CanvasImageSource

`CanvasImageSource` provides a mechanism for other interfaces to be used as image sources for some methods of the <span class="page-not-created">`CanvasDrawImage`</span> and <span class="page-not-created">`CanvasFillStrokeStyles`</span> interfaces. It’s just an internal helper type to simplify the specification. It’s not an interface and there are no objects implementing it.

The interfaces that it allows to be used as image sources are the following:

- [`HTMLImageElement`](htmlimageelement)
- [`SVGImageElement`](svgimageelement)
- [`HTMLVideoElement`](htmlvideoelement)
- [`HTMLCanvasElement`](htmlcanvaselement)
- [`ImageBitmap`](imagebitmap)
- [`OffscreenCanvas`](offscreencanvas)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#canvasimagesource">HTML Living Standard<br />
<span class="small">The definition of 'CanvasImageSource' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasImageSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasImageSource</a>
