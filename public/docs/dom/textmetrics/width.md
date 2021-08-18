TextMetrics.width
=================

The read-only `width` property of the [`TextMetrics`](../textmetrics) interface contains the text's advance width (the width of that inline box) in CSS pixels.

Examples
--------

Given this [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element:

    <canvas id="canvas"></canvas>

... you can get a [`TextMetrics`](../textmetrics) object using the following code:

    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');

    let text = ctx.measureText('foo'); // TextMetrics object
    text.width; // 16;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#dom-textmetrics-width">HTML Living Standard<br />
<span class="small">The definition of 'TextMetrics.width' in that specification.</span></a></td></tr></tbody></table>

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

`width`

4

12

1.5

9

9

3.1

Yes

Yes

31

Yes

3.2

Yes

See also
--------

-   [`TextMetrics`](../textmetrics)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics/width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TextMetrics/width</a>
