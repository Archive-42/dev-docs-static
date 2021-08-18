TextMetrics.ideographicBaseline
===============================

The read-only `ideographicBaseline` property of the [`TextMetrics`](../textmetrics) interface is a `double` giving the distance from the horizontal line indicated by the [`CanvasRenderingContext2D.textBaseline`](../canvasrenderingcontext2d/textbaseline) property to the ideographic baseline of the line box, in CSS pixels.

Examples
--------

    const canvas = document.createElement('canvas');
    const ctx = canvas.getContext('2d');
    const text = ctx.measureText('foo'); // returns TextMetrics object

    text.ideographicBaseline; // -1.201171875;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-textmetrics-ideographicbaseline">HTML Living Standard<br />
<span class="small">The definition of 'TextMetrics.ideographicBaseline' in that specification.</span></a></td></tr></tbody></table>

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

`ideographicBaseline`

Yes

79

74

No

No

Yes

No

Yes

No

No

Yes

No

See also
--------

-   [`TextMetrics`](../textmetrics)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics/ideographicBaseline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics/ideographicBaseline</a>
