# EXT_disjoint_timer_query

The **EXT_disjoint_timer_query** extension is part of the [WebGL API](webgl_api) and provides a way to measure the duration of a set of GL commands, without stalling the rendering pipeline.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

**Availability:** This extension should be available in [WebGL1](webglrenderingcontext) contexts only. <span class="page-not-created">`EXT_disjoint_timer_query_webgl2`</span> is available in [WebGL 2](webgl2renderingcontext) contexts .

In WebGL 2, the <span class="page-not-created">`getQueryObject`</span> was renamed to <span class="page-not-created">`getQueryParameter`</span>.  
In WebGL 2, other queries (such as occlusion queries and primitive queries) are possible using [`WebGLQuery`](webglquery) objects.

## Types

This extension exposes a new type:

GLuint64EXT  
Unsigned 64-bit integer number.

## Constants

This extension exposes seven new constants.

`ext.QUERY_COUNTER_BITS_EXT`  
A [`GLint`](webgl_api/types) indicating the number of bits used to hold the query result for the given target.

`ext.CURRENT_QUERY_EXT`  
A [`WebGLQuery`](webglquery) object, which is the currently active query for the given target.

`ext.QUERY_RESULT_EXT`  
A [`GLuint64EXT`](webgl_api/types) containing the query result.

`ext.QUERY_RESULT_AVAILABLE_EXT`  
A [`GLboolean`](webgl_api/types) indicating whether or not a query result is available.

`ext.TIME_ELAPSED_EXT`  
Elapsed time (in nanoseconds).

`ext.TIMESTAMP_EXT`  
The current time.

`ext.GPU_DISJOINT_EXT`  
A [`GLboolean`](webgl_api/types) indicating whether or not the GPU performed any disjoint operation.

## Methods

This extension exposes eight new methods.

[`ext.createQueryEXT()`](ext_disjoint_timer_query/createqueryext)  
Creates a new [`WebGLTimerQueryEXT`](webglquery).

[`ext.deleteQueryEXT()`](ext_disjoint_timer_query/deletequeryext)  
Deletes a given [`WebGLTimerQueryEXT`](webglquery).

[`ext.isQueryEXT()`](ext_disjoint_timer_query/isqueryext)  
Returns `true` if a given object is a valid [`WebGLTimerQueryEXT`](webglquery).

[`ext.beginQueryEXT()`](ext_disjoint_timer_query/beginqueryext)  
The timer starts when all commands prior to `beginQueryEXT` have been fully executed.

[`ext.endQueryEXT()`](ext_disjoint_timer_query/endqueryext)  
The timer stops when all commands prior to `endQueryEXT` have been fully executed.

[`ext.queryCounterEXT()`](ext_disjoint_timer_query/querycounterext)  
Records the current time into the corresponding query object.

[`ext.getQueryEXT()`](ext_disjoint_timer_query/getqueryext)  
Returns information about a query target.

[`ext.getQueryObjectEXT()`](ext_disjoint_timer_query/getqueryobjectext)  
Return the state of a query object.

## Examples

    var ext = gl.getExtension('EXT_disjoint_timer_query');

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

`EXT_disjoint_timer_query`

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

`beginQueryEXT`

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

`createQueryEXT`

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

`deleteQueryEXT`

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

`endQueryEXT`

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

`isQueryEXT`

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

`queryCounterEXT`

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

- [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EXT_disjoint_timer_query" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EXT_disjoint_timer_query</a>
