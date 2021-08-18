# RenderingContext

`RenderingContext` is a WebIDL `typedef` which can refer to any one of the interfaces that represent a graphics rendering context within a [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element: [`CanvasRenderingContext2D`](canvasrenderingcontext2d), [`WebGLRenderingContext`](webglrenderingcontext), or [`WebGL2RenderingContext`](webgl2renderingcontext).

By using the shorthand `RenderingContext`, methods and properties which can make use of any of these interfaces can be specified and written more easily; since `<canvas>` supports several rendering systems, it's helpful from a specification and browser implementation perspective to have a shorthand that means "one of these interfaces."

As such, `RenderingContext` is an implementation detail, and isn't something web developers directly use. There is no `RenderingContext` interface, and there are no objects which implement type `RenderingContext`.

The primary use of this type is the definition of the `<canvas>` element's [`HTMLCanvasElement.getContext()`](htmlcanvaselement/getcontext) method, which returns a `RenderingContext` (meaning it returns any one of the rendering context types).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#renderingcontext">HTML Living Standard<br />
<span class="small">The definition of 'RenderingContext' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

## See also

- The rendering context interfaces: [`CanvasRenderingContext2D`](canvasrenderingcontext2d), [`WebGLRenderingContext`](webglrenderingcontext), and [`WebGL2RenderingContext`](webgl2renderingcontext)
- [Graphics on the Web](https://developer.mozilla.org/en-US/docs/Web/Guide/Graphics)
- [Canvas API](canvas_api) and [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas)
- [WebGL](webgl_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RenderingContext" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RenderingContext</a>
