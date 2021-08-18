# CanvasRenderingContext2D.scrollPathIntoView()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The ` CanvasRenderingContext2D``.scrollPathIntoView() ` method of the Canvas 2D API scrolls the current or given path into view. It is similar to [`Element.scrollIntoView()`](../element/scrollintoview).

## Syntax

    void ctx.scrollPathIntoView();
    void ctx.scrollPathIntoView(path);

### Parameters

`path`  
A [`Path2D`](../path2d) path to use.

## Examples

### Using the scrollPathIntoView method

This example demonstrates the `scrollPathIntoView()` method.

#### HTML

    <canvas id="canvas"></canvas>

#### JavaScript

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    ctx.beginPath();
    ctx.fillRect(10, 10, 30, 30);
    ctx.scrollPathIntoView();

Edit the code below to see your changes update live in the canvas:

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-scrollpathintoview">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.scrollPathIntoView' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`scrollPathIntoView`

36

≤79

No

No

23

No

No

36

No

No

No

No

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`Element.scrollIntoView()`](../element/scrollintoview)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/scrollPathIntoView" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/scrollPathIntoView</a>
