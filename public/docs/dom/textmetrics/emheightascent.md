TextMetrics.emHeightAscent
==========================

The read-only `emHeightAscent` property of the [`TextMetrics`](../textmetrics) interface is a `double` giving the distance from the horizontal line indicated by the [`CanvasRenderingContext2D.textBaseline`](../canvasrenderingcontext2d/textbaseline) property to the top of the *em* square in the line box, in CSS pixels.

Examples
--------

    const canvas = document.createElement('canvas');
    const ctx = canvas.getContext('2d');
    const text = ctx.measureText('foo'); // returns TextMetrics object

    text.emHeightAscent; // 7.59765625;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-textmetrics-emheightascent">HTML Living Standard<br />
<span class="small">The definition of 'TextMetrics.emHeightAscent' in that specification.</span></a></td></tr></tbody></table>

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

`emHeightAscent`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics/emHeightAscent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics/emHeightAscent</a>
