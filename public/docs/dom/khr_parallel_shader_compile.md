# KHR_parallel_shader_compile

**Draft**

This page is not complete.

The `KHR_parallel_shader_compile` extension is part of the [WebGL API](webgl_api) and enables a non-blocking poll operation, so that compile/link status availability (`COMPLETION_STATUS_KHR`) can be queried without potentially incurring stalls. In other words you can check the status of your shaders compiling without blocking the runtime.

WebGL extensions are available using the [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension) method. For more information, see also [Using Extensions](webgl_api/using_extensions) in the [WebGL tutorial](webgl_api/tutorial).

## Constants

`ext.COMPLETION_STATUS_KHR`  
A GLenum.

## Examples

Enable the extension:

    var ext = gl.getExtension('KHR_parallel_shader_compile');

In general, best practice with or without the extension is:

    // Assuming lists of `shaders` and `programs`:
    for (const x of shaders)
        gl.compileShader(x); // Never check compile status unless subsequent linking fails.
    for (const x of programs)
        gl.linkProgram(x);

With the extension, apps would be able to poll whether programs have linked without janking, but these are likely to take the same total wall time to link:

    // Generator yielding a progress ratio [0.0, 1.0].
    // Without the extension, this will jank and only check one program per generation.
    function* linkingProgress(programs) {
        const ext = gl.getExtension('KHR_parallel_shader_compile');
        let todo = programs.slice();
        while (todo.length) {
            if (ext) {
                todo = todo.filter(x => !gl.getProgramParameter(x, ext.COMPLETION_STATUS_KHR));
            } else {
                const x = todo.pop();
                gl.getProgramParameter(x, gl.LINK_STATUS);
            }
            if (!todo.length)
                return;
            yield 1.0 - (todo.length / programs.length);
        }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/KHR_parallel_shader_compile/">KHR_parallel_shader_compile<br />
<span class="small">The definition of 'KHR_parallel_shader_compile' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`KHR_parallel_shader_compile`

76

79

80

No

63

14.1

76

76

No

?

14.5

12.0

## See also

- [`WebGLRenderingContext.getExtension()`](webglrenderingcontext/getextension)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/KHR_parallel_shader_compile" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/KHR_parallel_shader_compile</a>
