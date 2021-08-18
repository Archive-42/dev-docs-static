TextMetrics.fontBoundingBoxDescent
==================================

The read-only `fontBoundingBoxDescent` property of the [`TextMetrics`](../textmetrics) interface is a `double` giving the distance from the horizontal line indicated by the [`CanvasRenderingContext2D.textBaseline`](../canvasrenderingcontext2d/textbaseline) attribute to the bottom of the bounding rectangle of all the fonts used to render the text, in CSS pixels.

Examples
--------

    const canvas = document.createElement('canvas');
    const ctx = canvas.getContext('2d');
    const text = ctx.measureText('foo'); // returns TextMetrics object

    text.fontBoundingBoxDescent; // 3;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-textmetrics-fontboundingboxdescent">HTML Living Standard<br />
<span class="small">The definition of 'TextMetrics.fontBoundingBoxDescent' in that specification.</span></a></td></tr></tbody></table>

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

`fontBoundingBoxDescent`

87

Yes

79

74

No

73

Yes

87

87

Yes

No

No

No

14.0

See also
--------

-   [`TextMetrics`](../textmetrics)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics/fontBoundingBoxDescent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics/fontBoundingBoxDescent</a>
