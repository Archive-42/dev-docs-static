WebGL2RenderingContext.beginQuery()
===================================

The `WebGL2RenderingContext.beginQuery()` method of the [WebGL 2 API](../webgl_api) starts an asynchronous query. The `target` parameter indicates which kind of query to begin.

Syntax
------

    void gl.beginQuery(target, query);

### Parameters

target  
A [`GLenum`](../webgl_api/types) specifying the target of the query. Possible values:

-   `gl.ANY_SAMPLES_PASSED`: Specifies an occlusion query: these queries detect whether an object is visible (whether the scoped drawing commands pass the depth test and if so, how many samples pass).
-   `gl.ANY_SAMPLES_PASSED_CONSERVATIVE`: Same as above above, but less accurate and faster version.
-   `gl.TRANSFORM_FEEDBACK_PRIMITIVES_WRITTEN`: Number of primitives that are written to transform feedback buffers.

`query`  
A [`WebGLQuery`](../webglquery) object for which to start the querying.

### Return value

None.

Examples
--------

    var query = gl.createQuery();
    gl.beginQuery(gl.ANY_SAMPLES_PASSED, query);

    // ...

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.12">WebGL 2.0<br />
<span class="small">The definition of 'beginQuery' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glBeginQuery.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glBeginQuery' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`beginQuery`

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

-   [`WebGLQuery`](../webglquery)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/beginQuery" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/beginQuery</a>
