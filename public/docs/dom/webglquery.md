WebGLQuery
==========

The `WebGLQuery` interface is part of the [WebGL 2](webgl_api) API and provides ways to asynchronously query for information. By default, occlusion queries and primitive queries are available.

Another kind of queries are disjoint timer queries, which allow you to measure performance and profiling of your GPU. Disjoint timer queries are available with the [`EXT_disjoint_timer_query`](ext_disjoint_timer_query) extension only.

When working with `WebGLQuery` objects, the following methods of the [`WebGL2RenderingContext`](webgl2renderingcontext) are useful:

-   [`WebGL2RenderingContext.createQuery()`](webgl2renderingcontext/createquery)
-   [`WebGL2RenderingContext.deleteQuery()`](webgl2renderingcontext/deletequery)
-   [`WebGL2RenderingContext.isQuery()`](webgl2renderingcontext/isquery)
-   [`WebGL2RenderingContext.beginQuery()`](webgl2renderingcontext/beginquery)
-   [`WebGL2RenderingContext.endQuery()`](webgl2renderingcontext/endquery)
-   [`WebGL2RenderingContext.getQuery()`](webgl2renderingcontext/getquery)
-   [`WebGL2RenderingContext.getQueryParameter()`](webgl2renderingcontext/getqueryparameter)

Examples
--------

### Creating a `WebGLQuery` object

in this example, `gl` must be a [`WebGL2RenderingContext`](webgl2renderingcontext). `WebGLQuery` objects are not available in WebGL 1.

    var query = gl.createQuery();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.2">WebGL 2.0<br />
<span class="small">The definition of 'WebGLQuery' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`WebGLQuery`

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

-   [`EXT_disjoint_timer_query`](ext_disjoint_timer_query)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGLQuery" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGLQuery</a>
