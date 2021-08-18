WEBGL\_debug\_shaders.getTranslatedShaderSource()
=================================================

The `WEBGL_debug_shaders.getTranslatedShaderSource()` method is part of the [WebGL API](../webgl_api) and allows you to debug a translated shader.

Syntax
------

    gl.getExtension('WEBGL_debug_shaders').getTranslatedShaderSource(shader);

### Parameters

shader  
A [`WebGLShader`](../webglshader) to get the translated source from.

### Return value

A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) containing the translated shader source. An empty string is returned, if:

-   no source has been defined or,
-   [`WebGLRenderingContext.compileShader()`](../webglrenderingcontext/compileshader) has not yet been called or,
-   the translation for the shader failed.

Examples
--------

    var canvas = document.getElementById('canvas');
    var gl = canvas.getContext('webgl');

    var shader = gl.createShader(gl.FRAGMENT_SHADER);
    gl.shaderSource(shader, 'void main() { gl_FragColor = vec4(gl_FragCoord.x, 0.0, 0.0, 1.0); }');
    gl.compileShader(shader);

    var src = gl.getExtension('WEBGL_debug_shaders').getTranslatedShaderSource(shader);
    console.log(src);
    // "void main(){
    // (gl_FragColor = vec4(gl_FragCoord.x, 0.0, 0.0, 1.0));
    // }"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_debug_shaders/">WEBGL_debug_shaders<br />
<span class="small">The definition of 'WEBGL_debug_shaders.getTranslatedShaderSource' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getTranslatedShaderSource`

47

79

30

The extension is activated by default to privileged contexts (chrome context).

No

?

14

47

47

?

?

14

5.0

See also
--------

-   [`WebGLShader`](../webglshader)
-   [`WebGLRenderingContext.compileShader()`](../webglrenderingcontext/compileshader)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_debug_shaders/getTranslatedShaderSource" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_debug_shaders/getTranslatedShaderSource</a>
