OES\_element\_index\_uint
=========================

The `OES_element_index_uint` extension is part of the [WebGL API](webgl_api) and adds support for `gl.UNSIGNED_INT` types to [`WebGLRenderingContext.drawElements()`](webglrenderingcontext/drawelements).

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is only available to [WebGL1](webglrenderingcontext) contexts. In [WebGL2](webgl2renderingcontext), the functionality of this extension is available on the WebGL2 context by default.

Extended methods
----------------

This extension extends [`WebGLRenderingContext.drawElements()`](webglrenderingcontext/drawelements):

-   The `type` parameter now accepts `gl.UNSIGNED_INT`.

Examples
--------

    var ext = gl.getExtension('OES_element_index_uint');

    gl.drawElements(gl.POINTS, 8, gl.UNSIGNED_INT, 0);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/OES_element_index_uint/">OES_element_index_uint<br />
<span class="small">The definition of 'OES_element_index_uint' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`OES_element_index_uint`

24

12

24

11

15

8

≤37

25

?

14

8

1.5

See also
--------

-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.drawElements()`](webglrenderingcontext/drawelements)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OES_element_index_uint" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OES_element_index_uint</a>
