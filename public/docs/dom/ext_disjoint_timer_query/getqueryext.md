# EXT_disjoint_timer_query.getQueryEXT()

The `EXT_disjoint_timer_query.getQueryEXT()` method of the [WebGL API](../webgl_api) returns information about a query target.

## Syntax

    any ext.getQueryEXT(target, pname);

### Parameters

target  
A [`GLenum`](../webgl_api/types) specifying the target of the time query. Must be `ext.TIMESTAMP_EXT` or `ext.TIME_ELAPSED_EXT`.

`pname`  
A [`GLenum`](../webgl_api/types) specifying which information to return. Must be `ext.CURRENT_QUERY_EXT` or `ext.QUERY_COUNTER_BITS_EXT`.

### Return value

Depends on `pname`:

- If `pname` is `ext.CURRENT_QUERY_EXT`: A [`WebGLTimerQueryEXT`](../webglquery) object, which is the currently active query for the given target.
- If `pname` is `ext.QUERY_COUNTER_BITS_EXT`: A [`GLint`](../webgl_api/types) indicating the number of bits used to hold the query result for the given target.

## Examples

    var ext = gl.getExtension('EXT_disjoint_timer_query');
    var startQuery = ext.createQueryEXT();
    ext.queryCounterEXT(startQuery, ext.TIMESTAMP_EXT);

    var currentQuery = ext.getQueryEXT(ext.TIMESTAMP_EXT,
                                       ext.CURRENT_QUERY_EXT);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/EXT_disjoint_timer_query/">EXT_disjoint_timer_query<br />
<span class="small">The definition of 'EXT_disjoint_timer_query' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`getQueryEXT`

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

## See also

- [`WebGLRenderingContext.getExtension()`](../webglrenderingcontext/getextension)
- [`WebGLTimerQueryEXT`](../webglquery)
- [`EXT_disjoint_timer_query`](../ext_disjoint_timer_query)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EXT_disjoint_timer_query/getQueryEXT" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EXT_disjoint_timer_query/getQueryEXT</a>
