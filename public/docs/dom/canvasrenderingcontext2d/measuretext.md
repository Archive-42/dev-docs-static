# CanvasRenderingContext2D.measureText()

The `CanvasRenderingContext2D.measureText()` method returns a [`TextMetrics`](../textmetrics) object that contains information about the measured text (such as its width, for example).

## Syntax

    ctx.measureText(text);

### Parameters

`text`  
The text [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) to measure.

### Return value

A [`TextMetrics`](../textmetrics) object.

## Example

Given this [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element:

    <canvas id="canvas"></canvas>

... you can get a [`TextMetrics`](../textmetrics) object using the following code:

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    let text = ctx.measureText('Hello world');
    console.log(text.width);  // 56;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-context-2d-measuretext">HTML Living Standard<br />
<span class="small">The definition of 'CanvasRenderingContext2D.measureText' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`measureText`

1

12

2

9

≤12.1

4

1

18

4

≤12.1

3.2

1.0

## See also

- The interface defining this method: [`CanvasRenderingContext2D`](../canvasrenderingcontext2d)
- [`TextMetrics`](../textmetrics)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/measureText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D/measureText</a>
