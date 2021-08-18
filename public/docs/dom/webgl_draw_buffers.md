WEBGL\_draw\_buffers
====================

The `WEBGL_draw_buffers` extension is part of the [WebGL API](webgl_api) and enables a fragment shader to write to several textures, which is useful for [deferred shading](https://hacks.mozilla.org/2014/01/webgl-deferred-shading/), for example.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension is only available to [WebGL1](webglrenderingcontext) contexts. In [WebGL2](webgl2renderingcontext), the functionality of this extension is available on the WebGL2 context by default. In WebGL 2, the constants are available without the "WEBGL" suffix and the new GLSL built-ins require GLSL `#version 300 es`.

Constants
---------

This extension exposes new constants, which can be used in the [`gl.framebufferRenderbuffer()`](webglrenderingcontext/framebufferrenderbuffer), [`gl.framebufferTexture2D()`](webglrenderingcontext/framebuffertexture2d), [`gl.getFramebufferAttachmentParameter()`](webglrenderingcontext/getframebufferattachmentparameter) [`ext.drawBuffersWEBGL()`](webgl_draw_buffers/drawbufferswebgl), and [`gl.getParameter()`](webglrenderingcontext/getparameter) methods.

`ext.COLOR_ATTACHMENT0_WEBGL  ext.COLOR_ATTACHMENT1_WEBGL  ext.COLOR_ATTACHMENT2_WEBGL  ext.COLOR_ATTACHMENT3_WEBGL  ext.COLOR_ATTACHMENT4_WEBGL  ext.COLOR_ATTACHMENT5_WEBGL  ext.COLOR_ATTACHMENT6_WEBGL  ext.COLOR_ATTACHMENT7_WEBGL  ext.COLOR_ATTACHMENT8_WEBGL  ext.COLOR_ATTACHMENT9_WEBGL  ext.COLOR_ATTACHMENT10_WEBGL  ext.COLOR_ATTACHMENT11_WEBGL  ext.COLOR_ATTACHMENT12_WEBGL  ext.COLOR_ATTACHMENT13_WEBGL  ext.COLOR_ATTACHMENT14_WEBGL  ext.COLOR_ATTACHMENT15_WEBGL`  
A [`GLenum`](webgl_api/types) specifying a color buffer.

`ext.DRAW_BUFFER0_WEBGL  ext.DRAW_BUFFER1_WEBGL  ext.DRAW_BUFFER2_WEBGL  ext.DRAW_BUFFER3_WEBGL  ext.DRAW_BUFFER4_WEBGL  ext.DRAW_BUFFER5_WEBGL  ext.DRAW_BUFFER6_WEBGL  ext.DRAW_BUFFER7_WEBGL  ext.DRAW_BUFFER8_WEBGL  ext.DRAW_BUFFER9_WEBGL  ext.DRAW_BUFFER10_WEBGL  ext.DRAW_BUFFER11_WEBGL  ext.DRAW_BUFFER12_WEBGL  ext.DRAW_BUFFER13_WEBGL  ext.DRAW_BUFFER14_WEBGL  ext.DRAW_BUFFER15_WEBGL`  
A [`GLenum`](webgl_api/types) returning a draw buffer.

`ext.MAX_COLOR_ATTACHMENTS_WEBGL`  
A [`GLint`](webgl_api/types) indicating the maximum number of framebuffer color attachment points.

`ext.MAX_DRAW_BUFFERS_WEBGL`  
A [`GLint`](webgl_api/types) indicating the maximum number of draw buffers.

Methods
-------

This extension exposes one new method.

[`ext.drawBuffersWEBGL()`](webgl_draw_buffers/drawbufferswebgl)  
Defines the draw buffers to which all fragment colors are written. (When using [`WebGL2`](webgl2renderingcontext), this method is available as [`gl.drawBuffers()`](webgl2renderingcontext/drawbuffers) by default).

Examples
--------

Enabling the extension:

    var ext = gl.getExtension('WEBGL_draw_buffers');

Binding multiple textures (to a `tx[]` array) to different framebuffer color attachments:

    var fb = gl.createFramebuffer();
    gl.bindFramebuffer(gl.FRAMEBUFFER, fb);
    gl.framebufferTexture2D(gl.FRAMEBUFFER, ext.COLOR_ATTACHMENT0_WEBGL, gl.TEXTURE_2D, tx[0], 0);
    gl.framebufferTexture2D(gl.FRAMEBUFFER, ext.COLOR_ATTACHMENT1_WEBGL, gl.TEXTURE_2D, tx[1], 0);
    gl.framebufferTexture2D(gl.FRAMEBUFFER, ext.COLOR_ATTACHMENT2_WEBGL, gl.TEXTURE_2D, tx[2], 0);
    gl.framebufferTexture2D(gl.FRAMEBUFFER, ext.COLOR_ATTACHMENT3_WEBGL, gl.TEXTURE_2D, tx[3], 0);

Mapping the color attachments to draw buffer slots that the fragment shader will write to using `gl_FragData`:

    ext.drawBuffersWEBGL([
      ext.COLOR_ATTACHMENT0_WEBGL, // gl_FragData[0]
      ext.COLOR_ATTACHMENT1_WEBGL, // gl_FragData[1]
      ext.COLOR_ATTACHMENT2_WEBGL, // gl_FragData[2]
      ext.COLOR_ATTACHMENT3_WEBGL  // gl_FragData[3]
    ]);

Shader code that writes to multiple textures:

    <script type="x-shader/x-fragment">
    #extension GL_EXT_draw_buffers : require

    precision highp float;

    void main(void) {
      gl_FragData[0] = vec4(0.25);
      gl_FragData[1] = vec4(0.5);
      gl_FragData[2] = vec4(0.75);
      gl_FragData[3] = vec4(1.0);
    }
    </script>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_draw_buffers/">WEBGL_draw_buffers<br />
<span class="small">The definition of 'WEBGL_draw_buffers' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WEBGL_draw_buffers`

36

17

28

No

23

9

No

No

?

No

No

No

See also
--------

-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGL2RenderingContext.drawBuffers()`](webgl2renderingcontext/drawbuffers)
-   [WebGL deferred shading - Mozilla Hacks blog](https://hacks.mozilla.org/2014/01/webgl-deferred-shading/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_draw_buffers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_draw_buffers</a>
