# CanvasRenderingContext2D.drawWidgetAsOnScreen()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The non-standard and internal only `CanvasRenderingContext2D.drawWidgetAsOnScreen()` method of the Canvas 2D API renders the root widget of a window into the canvas. Unlike [`drawWindow()`](drawwindow), this API uses the operating system to snapshot the widget on-screen, rather than reading from Gecko's own compositor.

This API cannot be used by Web content. It is only supported on Windows, only on widgets that use [OMTC](https://wiki.mozilla.org/Platform/GFX/OffMainThreadCompositing), and only from within the chrome process.

## Syntax

    void ctx.drawWidgetAsOnScreen(window);

### Parameters

`window`  
The [`Window`](../window) to render.

## Specifications

Not part of any current specification or draft. This is a non-standard and internal only API.

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

`drawWidgetAsOnScreen`

No

No

41

No

No

No

No

No

41

No

No

No

## See also

- The interface defining it, [`CanvasRenderingContext2D`](../canvasrenderingcontext2d).
- [`CanvasRenderingContext2D.drawWindow()`](drawwindow)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/drawWidgetAsOnScreen" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/drawWidgetAsOnScreen</a>
