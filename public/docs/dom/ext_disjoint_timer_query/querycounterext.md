EXT\_disjoint\_timer\_query.queryCounterEXT()
=============================================

The `EXT_disjoint_timer_query.queryCounterEXT()` method of the [WebGL API](../webgl_api) records the current time into the corresponding query object.

Syntax
------

    void ext.queryCounterEXT(query, target);

### Parameters

`query`  
A [`WebGLTimerQueryEXT`](../webglquery) object for which to record the current time.

target  
A [`GLenum`](../webgl_api/types) specifying the target of the time query. Must be `ext.TIMESTAMP_EXT`.

### Return value

None.

Examples
--------

    var ext = gl.getExtension('EXT_disjoint_timer_query');
    var startQuery = ext.createQueryEXT();
    var endQuery = ext.createQueryEXT();
    ext.queryCounterEXT(startQuery, ext.TIMESTAMP_EXT);

    // ...

    ext.queryCounterEXT(endQuery, ext.TIMESTAMP_EXT);

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

See also
--------

-   [`WebGLRenderingContext.getExtension()`](../webglrenderingcontext/getextension)
-   [`WebGLTimerQueryEXT`](../webglquery)
-   [`EXT_disjoint_timer_query`](../ext_disjoint_timer_query)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EXT_disjoint_timer_query/queryCounterEXT" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EXT_disjoint_timer_query/queryCounterEXT</a>
