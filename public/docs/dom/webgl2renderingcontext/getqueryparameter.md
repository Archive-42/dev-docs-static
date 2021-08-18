WebGL2RenderingContext.getQueryParameter()
==========================================

The `WebGL2RenderingContext.getQueryParameter()` method of the [WebGL 2 API](../webgl_api) returns parameter information of a [`WebGLQuery`](../webglquery) object.

Syntax
------

    any gl.getQueryParameter(query, pname);

### Parameters

query  
A [`WebGLQuery`](../webglquery) object.

`pname`  
A [`GLenum`](../webgl_api/types) specifying which information to return. Possible values:

-   `gl.QUERY_RESULT`: Returns a [`GLuint`](../webgl_api/types) containing the query result.
-   `gl.QUERY_RESULT_AVAILABLE`: Returns a [`GLboolean`](../webgl_api/types) indicating whether or not a query result is available.

### Return value

Depends on the `pname` parameter, either a [`GLuint`](../webgl_api/types) or a [`GLboolean`](../webgl_api/types).

Examples
--------

    var query = gl.createQuery();
    gl.beginQuery(gl.ANY_SAMPLES_PASSED, query);

    var result = gl.getQueryParameter(query, gl.QUERY_RESULT);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.7.12">WebGL 2.0<br />
<span class="small">The definition of 'getQueryParameter' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.khronos.org/opengles/sdk/docs/man3/html/glGetQueryObjectuiv.xhtml">OpenGL ES 3.0<br />
<span class="small">The definition of 'glGetQueryObjectuiv' in that specification.</span></a></td><td><span class="spec-standard">Standard</span></td><td>Man page of the (similar) OpenGL API.</td></tr></tbody></table>

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

`getQueryParameter`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getQueryParameter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL2RenderingContext/getQueryParameter</a>
