# EXT_disjoint_timer_query.deleteQueryEXT()

The `EXT_disjoint_timer_query.deleteQueryEXT()` method of the [WebGL API](../webgl_api) deletes a given [`WebGLTimerQueryEXT`](../webglquery) object.

## Syntax

    void ext.deleteQueryEXT(query);

### Parameters

`query`  
A [`WebGLTimerQueryEXT`](../webglquery) object to delete.

### Return value

None.

## Examples

    var ext = gl.getExtension('EXT_disjoint_timer_query');
    var query = ext.createQueryEXT();

    // ...

    ext.deleteQueryEXT(query);

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

## See also

- [`WebGLRenderingContext.getExtension()`](../webglrenderingcontext/getextension)
- [`WebGLTimerQueryEXT`](../webglquery)
- [`EXT_disjoint_timer_query`](../ext_disjoint_timer_query)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EXT_disjoint_timer_query/deleteQueryEXT" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EXT_disjoint_timer_query/deleteQueryEXT</a>
