# HTMLCanvasElement: webglcontextlost event

The `webglcontextlost` event of the [WebGL API](../webgl_api) is fired if the user agent detects that the drawing buffer associated with a [`WebGLRenderingContext`](../webglrenderingcontext) object has been lost.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../webglcontextevent"><code>WebGLContextEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td>none</td></tr></tbody></table>

## Example

With the help of the [`WEBGL_lose_context`](../webgl_lose_context) extension, you can simulate the `webglcontextlost` event:

    const canvas = document.getElementById('canvas');
    const gl = canvas.getContext('webgl');

    canvas.addEventListener('webglcontextlost', (event) => {
      console.log(event);
    });

    gl.getExtension('WEBGL_lose_context').loseContext();

    // "webglcontextlost" event is logged.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.15.2">WebGL 1.0<br />
<span class="small">The definition of 'webglcontextlost' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`webglcontextlost_event`

9

12

4

11

12

5.1

≤37

25

4

12

8

1.5

## See also

- [`WebGLContextEvent`](../webglcontextevent)
- [`WebGLRenderingContext.isContextLost()`](../webglrenderingcontext/iscontextlost)
- [`WEBGL_lose_context`](../webgl_lose_context), [`WEBGL_lose_context.loseContext()`](../webgl_lose_context/losecontext), [`WEBGL_lose_context.restoreContext()`](../webgl_lose_context/restorecontext)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/webglcontextlost_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLCanvasElement/webglcontextlost_event</a>
