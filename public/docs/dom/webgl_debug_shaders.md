WEBGL\_debug\_shaders
=====================

The `WEBGL_debug_shaders` extension is part of the [WebGL API](webgl_api) and exposes a method to debug shaders from privileged contexts.

This extension is not directly available to web sites as the way of how the shader is translated may uncover personally-identifiable information to the web page about the kind of graphics card in the user's computer.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** Depending on the privacy settings of the browser, this extension might only be available to privileged contexts.

This extension is available to both, [WebGL1](webglrenderingcontext) and [WebGL2](webgl2renderingcontext) contexts.

Methods
-------

[`WEBGL_debug_shaders.getTranslatedShaderSource()`](webgl_debug_shaders/gettranslatedshadersource)  
Returns the translated shader source.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/WEBGL_debug_shaders/">WEBGL_debug_shaders<br />
<span class="small">The definition of 'WEBGL_debug_shaders' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WEBGL_debug_shaders`

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

-   [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_debug_shaders" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WEBGL_debug_shaders</a>
