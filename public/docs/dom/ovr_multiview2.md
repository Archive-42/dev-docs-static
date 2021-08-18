OVR\_multiview2
===============

The `OVR_multiview2` extension is part of the [WebGL API](webgl_api) and adds support for rendering into multiple views simultaneously. This especially useful for virtual reality (VR) and WebXR.

For more information, see also:

-   [Multiview on WebXR](https://blog.mozvr.com/multiview-on-webxr/)
-   [three.js multiview demo](https://threejs.org/examples/webxr_vr_multiview)
-   [Multiview in babylon.js](https://doc.babylonjs.com/how_to/multiview)
-   [Optimizing Virtual Reality: Understanding Multiview](https://community.arm.com/developer/tools-software/graphics/b/blog/posts/optimizing-virtual-reality-understanding-multiview)
-   [Multiview WebGL Rendering for Oculus Browser 6.0+](https://developer.oculus.com/documentation/oculus-browser/latest/concepts/browser-multiview/)

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** Support depends on the system's graphics driver (Windows+ANGLE and Android are supported; Windows+GL, Mac, Linux are not supported).

This extension is only available to [WebGL 2](webgl2renderingcontext) contexts as it needs GLSL 3.00 and texture arrays.  
  
Currently, there is no way to use multiview to render to a multisampled backbuffer, so you should create contexts with `antialias: false`. However, the Oculus browser (6+) also supports multisampling using the `OCULUS_multiview` extension. See also [this WebGL issue](https://github.com/KhronosGroup/WebGL/issues/2912).

Constants
---------

This extension exposes 4 constants that can be used in `getParameter()` or `getFramebufferAttachmentParameter()`.

`FRAMEBUFFER_ATTACHMENT_TEXTURE_NUM_VIEWS_OVR`  
Number of views of the framebuffer object attachment.

`FRAMEBUFFER_ATTACHMENT_TEXTURE_BASE_VIEW_INDEX_OVR`  
Base view index of the framebuffer object attachment.

`MAX_VIEWS_OVR`  
The maximum number of views. Most VR headsets have two views, but there are prototypes of headset with ultra-wide FOV using 4 views which is currently the maximum number of views supported by multiview.

`FRAMEBUFFER_INCOMPLETE_VIEW_TARGETS_OVR`  
If baseViewIndex is not the same for all framebuffer attachment points where the value of `FRAMEBUFFER_ATTACHMENT_OBJECT_TYPE` is not `NONE`, the framebuffer is considered incomplete. Calling `checkFramebufferStatus` for a framebuffer in this state returns `FRAMEBUFFER_INCOMPLETE_VIEW_TARGETS_OVR`.

Methods
-------

`framebufferTextureMultiviewOVR()`  
Simultaneously renders to multiple elements of a 2D texture array.

Examples
--------

This example is taken from the [specification](https://www.khronos.org/registry/webgl/extensions/OVR_multiview2/). See also this [three.js](https://threejs.org/examples/webvr_multiview.html) demo for a live multiview example.

    const gl = document.createElement('canvas').getContext( 'webgl2', { antialias: false } );
    const ext = gl.getExtension('OVR_multiview2');
    const fb = gl.createFramebuffer();
    gl.bindFramebuffer(gl.DRAW_FRAMEBUFFER, fb);

    const colorTex = gl.createTexture();
    gl.bindTexture(gl.TEXTURE_2D_ARRAY, colorTex);
    gl.texStorage3D(gl.TEXTURE_2D_ARRAY, 1, gl.RGBA8, 512, 512, 2);
    ext.framebufferTextureMultiviewOVR(gl.DRAW_FRAMEBUFFER, gl.COLOR_ATTACHMENT0, colorTex, 0, 0, 2);

    const depthStencilTex = gl.createTexture();
    gl.bindTexture(gl.TEXTURE_2D_ARRAY, depthStencilTex);
    gl.texStorage3D(gl.TEXTURE_2D_ARRAY, 1, gl.DEPTH32F_STENCIL8, 512, 512, 2);

    ext.framebufferTextureMultiviewOVR(gl.DRAW_FRAMEBUFFER, gl.DEPTH_STENCIL_ATTACHMENT, depthStencilTex, 0, 0, 2);
    gl.drawElements(...);  // draw will be broadcasted to the layers of colorTex and depthStencilTex.    

Shader code

    #version 300 es
    #extension GL_OVR_multiview2 : require
    precision mediump float;
    layout (num_views = 2) in;
    in vec4 inPos;
    uniform mat4 u_viewMatrices[2];
    void main() {
      gl_Position = u_viewMatrices[gl_ViewID_OVR] * inPos;
    }    

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/OVR_multiview2/">OVR_multiview2</a></td><td>Community Approved</td></tr></tbody></table>

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

`OVR_multiview2`

75

70-75

79

71

No

No

No

75

70-75

75

70-75

No

No

No

11.0

10.0-11.0

`framebufferTextureMultiviewOVR`

75

70-75

79

71

No

No

No

75

70-75

75

70-75

No

No

No

11.0

10.0-11.0

See also
--------

-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)
-   [`WebGLRenderingContext.getParameter()`](webglrenderingcontext/getparameter)
-   [WebXR](webxr_device_api)
-   [three.js multiview demo](https://threejs.org/examples/webxr_vr_multiview)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OVR_multiview2" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OVR_multiview2</a>
