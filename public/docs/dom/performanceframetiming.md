PerformanceFrameTiming
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

`PerformanceFrameTiming` is an *abstract* interface that provides *frame* timing data about the browser's event loop. A *frame* represents the amount of work a browser does in [one event loop](https://html.spec.whatwg.org/multipage/webappapis.html#processing-model-8) such as processing DOM events, resizing, scrolling, rendering, CSS animations, etc.. A *frame rate* of 60fps (frames per second) for a 60Hz refresh rate is the target for a good *responsive* user experience. This means the browser should process a frame in about 16.7ms.

An application can register a [`PerformanceObserver`](performanceobserver) for "`frame`" [`performance entry types`](performanceentry) and the observer can retrieve data about the duration of each frame event. This information can be used to help identify areas that take too long to provide a good user experience.

Properties
----------

This interface has no properties but it extends the following [`PerformanceEntry`](performanceentry) properties (for "`frame`" [`performance entry types`](performanceentry/entrytype)) by qualifying and constraining the properties as follows:

[`PerformanceEntry.entryType`](performanceentry/entrytype)  
Returns "`frame`".

[`PerformanceEntry.name`](performanceentry/name)  
Returns the [document's address](https://dom.spec.whatwg.org/#concept-document-url).

[`PerformanceEntry.startTime`](performanceentry/starttime)  
Returns the [`timestamp`](domhighrestimestamp) when the frame was started.

[`PerformanceEntry.duration`](performanceentry/duration)  
Returns a [`timestamp`](domhighrestimestamp) indicating the difference between the `startTime`s of two successive frames.

Methods
-------

This interface has no methods.

Example
-------

See the example in [Using the Frame Timing API](frame_timing_api/using_the_frame_timing_api).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/frame-timing/#performanceframetiming-interface">Frame Timing<br />
<span class="small">The definition of 'PerformanceFrameTiming' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PerformanceFrameTiming`

No

See [Chrome bug 120796](https://crbug.com/120796)

No

See [Chrome bug 120796](https://crbug.com/120796)

No

See [bug 1158032](https://bugzil.la/1158032)

No

No

No

No

See [Chrome bug 120796](https://crbug.com/120796)

No

See [Chrome bug 120796](https://crbug.com/120796)

No

No

No

No

See [Chrome bug 120796](https://crbug.com/120796)

See also
--------

-   [`PerformanceObserver`](performanceobserver)
-   [Frame Rate (Firefox Performance Tool)](https://developer.mozilla.org/en-US/docs/Tools/Performance/Frame_rate)
-   [Frame Timing (Overview)](frame_timing)
-   [Using the Frame Timing API](frame_timing_api/using_the_frame_timing_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceFrameTiming" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceFrameTiming</a>
