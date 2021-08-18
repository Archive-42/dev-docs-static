# OES_standard_derivatives

The `OES_standard_derivatives` extension is part of the [WebGL API](webgl_api) and adds the GLSL derivative functions `dFdx`, `dFdy`, and `fwidth`.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is only available to [WebGL1](webglrenderingcontext) contexts. In [WebGL2](webgl2renderingcontext), the functionality of this extension is available on the WebGL2 context by default. In WebGL 2, the constant is available as `gl.FRAGMENT_SHADER_DERIVATIVE_HINT` and it requires GLSL `#version 300 es`.

## Constants

This extension exposes one new constant, which can be used in the [`hint()`](webglrenderingcontext/hint) and [`getParameter()`](webglrenderingcontext/getparameter) methods.

`ext.FRAGMENT_SHADER_DERIVATIVE_HINT_OES`  
A [`WebGL_API.Types`](webgl_api/types) indicating the accuracy of the derivative calculation for the GLSL built-in functions: `dFdx`, `dFdy`, and `fwidth`.

## GLSL built-in functions

The following new functions can be used in GLSL shader code, if this extension is enabled:

    genType dFdx(genType)
    genType dFdy(genType)
    genType fwidth(genType)

## Examples

Enabling the extensions:

    gl.getExtension('OES_standard_derivatives');
    gl.getExtension('EXT_shader_texture_lod');

Shader code that avoids artifacts when wrapping texture coordinates:

    <script type="x-shader/x-fragment">
    #extension GL_EXT_shader_texture_lod : enable
    #extension GL_OES_standard_derivatives : enable

    uniform sampler2D myTexture;
    varying vec2 texcoord;

    void main(){
      gl_FragColor = texture2DGradEXT(myTexture, mod(texcoord, vec2(0.1, 0.5)),
                                      dFdx(texcoord), dFdy(texcoord));
    }
    </script>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/OES_standard_derivatives/">OES_standard_derivatives<br />
<span class="small">The definition of 'OES_standard_derivatives' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`OES_standard_derivatives`

10

≤18

10

11

15

8

≤37

18

?

No

8

1.0

## See also

- [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
- [`EXT_shader_texture_lod`](ext_shader_texture_lod)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OES_standard_derivatives" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OES_standard_derivatives</a>
