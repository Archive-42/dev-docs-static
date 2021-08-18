TextMetrics.actualBoundingBoxLeft
=================================

The read-only `actualBoundingBoxLeft` property of the [`TextMetrics`](../textmetrics) interface is a `double` giving the distance parallel to the baseline from the alignment point given by the [`CanvasRenderingContext2D.textAlign`](../canvasrenderingcontext2d/textalign) property to the left side of the bounding rectangle of the given text, in CSS pixels.

Examples
--------

    const canvas = document.createElement('canvas');
    const ctx = canvas.getContext('2d');
    const text = ctx.measureText('foo'); // returns TextMetrics object

    text.actualBoundingBoxLeft; // 0;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-textmetrics-actualboundingboxleft">HTML Living Standard<br />
<span class="small">The definition of 'TextMetrics.actualBoundingBoxLeft' in that specification.</span></a></td></tr></tbody></table>

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

`actualBoundingBoxLeft`

77

Yes-77

79

74

No

64

Yes

77

77

Yes-77

No

55

Yes

12.0

See also
--------

-   [`TextMetrics`](../textmetrics)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics/actualBoundingBoxLeft" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics/actualBoundingBoxLeft</a>
