# EXT_frag_depth

The `EXT_frag_depth` extension is part of the [WebGL API](webgl_api) and enables to set a depth value of a fragment from within the fragment shader.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is only available to [WebGL1](webglrenderingcontext) contexts. In [WebGL2](webgl2renderingcontext), the functionality of this extension is available on the WebGL2 context by default. It requires GLSL `#version 300 es`.

## Examples

Enable the extension:

    gl.getExtension('EXT_frag_depth');

Now the output variable `gl_FragDepthEXT` is available to set a depth value of a fragment from within the fragment shader:

    <script type="x-shader/x-fragment">
    void main() {
      gl_FragColor = vec4(1.0, 0.0, 1.0, 1.0);
      gl_FragDepthEXT = 0.5;
    }
    </script>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/EXT_frag_depth/">EXT_frag_depth<br />
<span class="small">The definition of 'EXT_frag_depth' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`EXT_frag_depth`

38

12-79

47

No

25

7

38

38

47

25

No

3.0

## See also

- [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EXT_frag_depth" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EXT_frag_depth</a>
