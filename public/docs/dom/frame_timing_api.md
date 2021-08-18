# Frame Timing API

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `PerformanceFrameTiming` interface provides _frame_ timing data about the browser's event loop. A _frame_ represents the amount of work a browser does in [one event loop iteration](https://html.spec.whatwg.org/multipage/webappapis.html#processing-model-8) such as processing DOM events, resizing, scrolling, rendering, CSS animations, etc. A _frame rate_ of 60 fps (frames per second) for a 60 Hz refresh rate is a common target for a good _responsive_ user experience. This means the browser should process a frame in about 16.7 ms.

An application can register a [`PerformanceObserver`](performanceobserver) for "`frame`" [`performance entry types`](performanceentry). The _observer_ (callback) will be notified when new "`frame`" events are added to the browser's _performance timeline_ and the frame's [`duration`](performanceentry/duration) (length of time) will be available. This data can be used to help identify areas that take too long to provide a good user experience.

Example code of the interfaces described in this document is included in _[Using the Frame Timing API](frame_timing_api/using_the_frame_timing_api)_.

## Performance `frames`

The [`PerformanceFrameTiming`](performanceframetiming) interface extends the following [`PerformanceEntry`](performanceentry) properties (for "`frame`" [`performance entry types`](performanceentry/entrytype)) by qualifying and constrainting the properties as follows:

[`PerformanceEntry.entryType`](performanceentry/entrytype)  
Set to "`frame`".

[`PerformanceEntry.name`](performanceentry/name)  
Set to the [document's address](https://dom.spec.whatwg.org/#concept-document-url).

[`PerformanceEntry.startTime`](performanceentry/starttime)  
Set to the [`DOMHighResTimeStamp`](domhighrestimestamp) when the frame was started.

[`PerformanceEntry.duration`](performanceentry/duration)  
Set to a [`timestamp`](domhighrestimestamp) indicating the difference between the `startTime`s of two successive frames.

This data, particularly the `duration` timestamp, can be used to help identify performance problems.

## Frame observers

<span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>The _performance observer_ interfaces allow an application to register an _observer_ for specific [`performance event types`](performanceentry). When one of those event types is recorded in the browser's _performance timeline_, the application is notified of the event via the observer's callback function that was specified when the observer was created.

To observe "`frame`" performance entry types, the application first creates a [`PerformanceObserver`](performanceobserver) object with a specific frame observer callback (function). Next, [`PerformanceObserver.observe()`](performanceobserver/observe) is used to specify the set of performance events to observe - in this case, just the "`frame`" event type. When the browser adds a new frame to the performance timeline, the specified observer callback will be invoked.

## Accessing frame data

When a frame [`observer`](performanceobserver) is invoked, frame [`performance entries`](performanceentry) can be retrieved by calling [`PerformanceObserverEntryList.getEntriesByType()`](performanceobserverentrylist/getentriesbytype) with an argument of "`frame`". This method returns a list of "`frame`" [`PerformanceEntry`](performanceentry) objects. Each frame object's [`duration`](performanceentry/duration) property returns the timestamp of two consecutive frames. If this value is greater than the time needed to provide a good user experience, further analysis might be warranted.

## Browser compatibility

## See also

- [Frame Rate (Firefox Performance Tool)](https://developer.mozilla.org/en-US/docs/Tools/Performance/Frame_rate)
- [Using the Frame Timing API](frame_timing_api/using_the_frame_timing_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Frame_Timing_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Frame_Timing_API</a>
