TextMetrics.actualBoundingBoxAscent
===================================

The read-only `actualBoundingBoxAscent` property of the [`TextMetrics`](../textmetrics) interface is a `double` giving the distance from the horizontal line indicated by the [`CanvasRenderingContext2D.textBaseline`](../canvasrenderingcontext2d/textbaseline) attribute to the top of the bounding rectangle used to render the text, in CSS pixels.

Examples
--------

    const canvas = document.createElement('canvas');
    const ctx = canvas.getContext('2d');
    const text = ctx.measureText('foo'); // returns TextMetrics object

    text.actualBoundingBoxAscent; // 8;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-textmetrics-actualboundingboxascent">HTML Living Standard<br />
<span class="small">The definition of 'TextMetrics.actualBoundingBoxAscent' in that specification.</span></a></td></tr></tbody></table>

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

`actualBoundingBoxAscent`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics/actualBoundingBoxAscent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics/actualBoundingBoxAscent</a>
