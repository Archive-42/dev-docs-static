WebGL2RenderingContext.bindSampler()
====================================

The `WebGL2RenderingContext.bindSampler()` method of the [WebGL 2 API](../webgl_api) binds a passed [`WebGLSampler`](../webglsampler) object to the texture unit at the passed index.

Syntax
------

    void gl.bindSampler(unit, sampler);

### Parameters

unit  
A [`GLuint`](../webgl_api/types) specifying the index of the texture unit to which to bind the sampler to.

sampler  
A [`WebGLSampler`](../webglsampler) object to bind.

### Return value

None.

Examples
--------

    var sampler = gl.createSampler();
    gl.bindSampler(0, sampler);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.13">WebGL 2.0<br />
<span class="small">The definition of 'bindSampler' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glBindSampler.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glBindSampler' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`bindSampler`

56

79

51

No

43

No

58

58

51

43

No

7.0

See also
--------

-   [`WebGLSampler`](../webglsampler)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/bindSampler" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/bindSampler</a>
