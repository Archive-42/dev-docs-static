# CanvasRenderingContext2D.getContextAttributes()

The `CanvasRenderingContext2D.getContextAttributes()` method returns an object that contains the actual context parameters. Context attributes can be requested with [`HTMLCanvasElement.getContext()`](../htmlcanvaselement/getcontext) on context creation.

## Syntax

    ctx.getContextAttributes();

### Return value

A `CanvasRenderingContext2DSettings` object that contains the actual context parameters. It has the following members:

`alpha`  
A Boolean indicating if the canvas contains an alpha channel. If `false`, the backdrop is always opaque, which can speed up drawing of transparent content and images.

`desynchronized`  
A Boolean indicating the user agent reduced the latency by desynchronizing the canvas paint cycle from the event loop.

## Examples

Given context attributes were provided on context creation using [`HTMLCanvasElement.getContext()`](../htmlcanvaselement/getcontext)

    let canvas = document.createElement('canvas');
    let ctx = canvas.getContext('2d', {alpha: false});

the `getContextAttributes()` method lets you read back actual attributes used by the user agent:

    ctx.getContextAttributes();
    // returns {alpha: false, desynchronized: false}

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-context-2d-canvas-getcontextattributes">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.getContextAttributes' in that specification.</span></a></td></tr></tbody></table>

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

`getContextAttributes`

73

32-60

79

No

No

60

19-47

No

73

4.4.3-60

73

32-60

No

52

19-44

No

11.0

2.0-8.0

## See also

- [`HTMLCanvasElement.getContext()`](../htmlcanvaselement/getcontext)
- [`WebGLRenderingContext.getContextAttributes()`](../webglrenderingcontext/getcontextattributes)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/getContextAttributes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/getContextAttributes</a>
