EXT\_shader\_texture\_lod
=========================

The `EXT_shader_texture_lod` extension is part of the [WebGL API](webgl_api) and adds additional texture functions to the OpenGL ES Shading Language which provide the shader writer with explicit control of LOD ([Level of detail](https://en.wikipedia.org/wiki/Level_of_detail)).

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is only available to [WebGL1](webglrenderingcontext) contexts. In [WebGL2](webgl2renderingcontext), the functionality of this extension is available on the WebGL2 context by default. It requires GLSL `#version 300 es`.

GLSL built-in functions
-----------------------

The following new functions can be used in GLSL shader code, if this extension is enabled:

    vec4 texture2DLodEXT(sampler2D sampler, vec2 coord, float lod)
    vec4 texture2DProjLodEXT(sampler2D sampler, vec3 coord, float lod)
    vec4 texture2DProjLodEXT(sampler2D sampler, vec4 coord, float lod)
    vec4 textureCubeLodEXT(samplerCube sampler, vec3 coord, float lod)
    vec4 texture2DGradEXT(sampler2D sampler, vec2 P, vec2 dPdx, vec2 dPdy)
    vec4 texture2DProjGradEXT(sampler2D sampler, vec3 P, vec2 dPdx, vec2 dPdy)
    vec4 texture2DProjGradEXT(sampler2D sampler, vec4 P, vec2 dPdx, vec2 dPdy)
    vec4 textureCubeGradEXT(samplerCube sampler, vec3 P, vec3 dPdx, vec3 dPdy)

Examples
--------

Enabling the extensions:

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/EXT_shader_texture_lod/">EXT_shader_texture_lod<br />
<span class="small">The definition of 'EXT_shader_texture_lod' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`EXT_shader_texture_lod`

38

17-79

47

No

25

8

38

38

47

25

8

3.0

See also
--------

-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`OES_standard_derivatives`](oes_standard_derivatives)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EXT_shader_texture_lod" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EXT_shader_texture_lod</a>
