TextMetrics.emHeightDescent
===========================

The read-only `emHeightDescent` property of the [`TextMetrics`](../textmetrics) interface is a `double` giving the distance from the horizontal line indicated by the [`CanvasRenderingContext2D.textBaseline`](../canvasrenderingcontext2d/textbaseline) property to the bottom of the *em* square in the line box, in CSS pixels.

Examples
--------

    const canvas = document.createElement('canvas');
    const ctx = canvas.getContext('2d');
    const text = ctx.measureText('foo'); // returns TextMetrics object

    text.emHeightDescent; // -2.40234375;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-textmetrics-emheightdescent">HTML Living Standard<br />
<span class="small">The definition of 'TextMetrics.emHeightDescent' in that specification.</span></a></td></tr></tbody></table>

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

`emHeightDescent`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics/emHeightDescent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics/emHeightDescent</a>
