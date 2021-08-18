EXT\_disjoint\_timer\_query.getQueryObjectEXT()
===============================================

The `EXT_disjoint_timer_query.getQueryObjectEXT()` method of the [WebGL API](../webgl_api) returns the state of a query object.

Syntax
------

    any ext.getQueryObjectEXT(query, pname);

### Parameters

`query`  
A [`WebGLTimerQueryEXT`](../webglquery) object from which to return information.

`pname`  
A [`GLenum`](../webgl_api/types) specifying which information to return. Must be `ext.QUERY_RESULT_EXT` or `ext.QUERY_RESULT_AVAILABLE_EXT`.

### Return value

Depends on `pname`:

-   If `pname` is `ext.QUERY_RESULT_EXT`: A [`GLuint64EXT`](../webgl_api/types) containing the query result.
-   If `pname` is `ext.QUERY_RESULT_AVAILABLE_EXT`: A [`GLboolean`](../webgl_api/types) indicating whether or not a query result is available.

Examples
--------

    var ext = gl.getExtension('EXT_disjoint_timer_query');
    var query = ext.createQueryEXT();
    ext.beginQueryEXT(ext.TIME_ELAPSED_EXT, query);

    // ... drawing ...

    ext.endQueryEXT(ext.TIME_ELAPSED_EXT);

    // At some point in the future, after returning control to the browser
    var available = ext.getQueryObjectEXT(query, ext.QUERY_RESULT_AVAILABLE_EXT);
    var disjoint = gl.getParameter(ext.GPU_DISJOINT_EXT);

    if (available && !disjoint) {
      // See how much time the rendering of the object took in nanoseconds.
      var timeElapsed = ext.getQueryObjectEXT(query, ext.QUERY_RESULT_EXT);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/EXT_disjoint_timer_query/">EXT_disjoint_timer_query<br />
<span class="small">The definition of 'EXT_disjoint_timer_query' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getQueryObjectEXT`

47-65

Removed due to the [GLitch exploit](https://www.vusec.net/projects/glitch/).

No

51-59

Removed due to the [GLitch exploit](https://www.vusec.net/projects/glitch/).

No

34-52

Removed due to the [GLitch exploit](https://www.vusec.net/projects/glitch/).

No

47-65

Removed due to the [GLitch exploit](https://www.vusec.net/projects/glitch/).

47-65

Removed due to the [GLitch exploit](https://www.vusec.net/projects/glitch/).

No

34-47

Removed due to the [GLitch exploit](https://www.vusec.net/projects/glitch/).

No

5.0-9.0

Removed due to the [GLitch exploit](https://www.vusec.net/projects/glitch/).

See also
--------

-   [`WebGLRenderingContext.getExtension()`](../webglrenderingcontext/getextension)
-   [`WebGLTimerQueryEXT`](../webglquery)
-   [`EXT_disjoint_timer_query`](../ext_disjoint_timer_query)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EXT_disjoint_timer_query/getQueryObjectEXT" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EXT_disjoint_timer_query/getQueryObjectEXT</a>
