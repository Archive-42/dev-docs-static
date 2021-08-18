TextMetrics.fontBoundingBoxAscent
=================================

The read-only `fontBoundingBoxAscent` property of the [`TextMetrics`](../textmetrics) interface is a `double` giving the distance from the horizontal line indicated by the [`CanvasRenderingContext2D.textBaseline`](../canvasrenderingcontext2d/textbaseline) attribute to the top of the highest bounding rectangle of all the fonts used to render the text, in CSS pixels.

Examples
--------

    const canvas = document.createElement('canvas');
    const ctx = canvas.getContext('2d');
    const text = ctx.measureText('foo'); // returns TextMetrics object

    text.fontBoundingBoxAscent; // 10;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-textmetrics-fontboundingboxascent">HTML Living Standard<br />
<span class="small">The definition of 'TextMetrics.fontBoundingBoxAscent' in that specification.</span></a></td></tr></tbody></table>

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

`fontBoundingBoxAscent`

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

Yes

14.0

See also
--------

-   [`TextMetrics`](../textmetrics)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics/fontBoundingBoxAscent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics/fontBoundingBoxAscent</a>
