# Performance API

The [High Resolution Time](https://www.w3.org/TR/hr-time/) standard defines a [`Performance`](performance) interface that supports client-side latency measurements within applications. The [`Performance`](performance) interfaces are considered _high resolution_ because they are accurate to a thousandth of a millisecond (subject to hardware or software constraints). The interfaces support a number of use cases including calculating frame-rates (potentially important in animations) and benchmarking (such as the time to load a resource).

Since a platform's _system clock_ is subject to various _skews_ (such as NTP adjustments), the interfaces support a _monotonic clock_ i.e. a clock that is always increasing. As such, the `Performance` API defines a [`DOMHighResTimeStamp`](domhighrestimestamp) type rather than using the [`Date.now()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/now) interface.

## DOMHighResTimeStamp

The [`DOMHighResTimeStamp`](domhighrestimestamp) type, as its name implies, represents a high resolution point in time. This type is a `double` and is used by the performance interfaces. The value could be a discrete point in time or the difference in time between two discrete points in time.

The unit of `DOMHighResTimeStamp` is milliseconds and should be accurate to 5 µs (microseconds). However, If the browser is unable to provide a time value accurate to 5 microseconds (because, for example, due to hardware or software constraints), the browser can represent the value as a time in milliseconds accurate to a millisecond.

## Methods

The `Performance` interface has two methods. The [`now()`](performance/now) method returns a [`DOMHighResTimeStamp`](domhighrestimestamp) whose value that depends on the [`navigation start`](performancetiming/navigationstart) and scope. If the scope is a window, the value is the time the browser context was created and if the scope is a [`worker`](worker), the value is the time the worker was created.

The [`toJSON()`](performance/tojson) method returns a serialization of the [`Performance`](performance) object, for those attributes that can be serialized.

## Properties

The `Performance` interface has two properties. The [`timing`](performance/timing) property returns a [`PerformanceTiming`](performancetiming) object containing latency-related performance information such as the start of navigation time, start and end times for redirects, start and end times for responses, etc.

The `navigation` property returns a [`PerformanceNavigation`](performancenavigation) object representing the type of navigation that occurs in the given browsing context, such as the page was navigated to from history, the page was navigated to by following a link, etc.

## Interfaces

[`Performance`](performance)  
Provides methods and properties containing timing-related performance information for the given page.

[`PerformanceEntry`](performanceentry)  
Provides methods and properties the encapsulate a single performance metric that is part of the performance timeline.

[`PerformanceFrameTiming`](performanceframetiming)  
Provides methods and properties containing frame timing data about the browser's event loop.

[`PerformanceMark`](performancemark)  
An abstract interface for [`performance entries`](performanceentry) with an [`entry type`](performanceentry/entrytype) of "`mark`". Entries of this type are created by calling [`performance.mark()`](performance/mark) to add a named [`DOMHighResTimeStamp`](domhighrestimestamp) (the mark) to the browser's performance timeline.

[`PerformanceMeasure`](performancemeasure)  
An abstract interface for [`performance entries`](performanceentry) with an [`entry type`](performanceentry/entrytype) of "`measure`". Entries of this type are created by calling [`performance.measure()`](performance/measure) to add a named[`DOMHighResTimeStamp`](domhighrestimestamp) (the measure) between two marks to the browser's performance timeline.

[`PerformanceNavigationTiming`](performancenavigationtiming)  
Provides methods and properties to store and retrieve [`high resolution timestamps`](domhighrestimestamp) or metrics regarding the browser's document navigation events.

[`PerformanceObserver`](performanceobserver)  
Provides methods and properties used to observe performance measurement events and be notified of new [performance entries](performanceentry) as they are recorded in the browser's performance timeline.

[`PerformanceResourceTiming`](performanceresourcetiming)  
Provides methods and properties for retrieving and analyzing detailed network timing data regarding the loading of an application's resources.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/hr-time-1/">High Resolution Time</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/hr-time-2/">High Resolution Time Level 2</a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds <code>performance</code> attribute on <code>Window</code> and <code>WorkerGlobalScope</code>.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/hr-time/">High Resolution Time Level 3</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Add <code>timeOrigin</code> property to <code>Performance</code> interface.</td></tr><tr class="even"><td><a href="https://wicg.github.io/frame-timing/">Frame Timing</a></td><td><span class="spec-draft">Draft</span></td><td>Adds <code>PerformanceFrameTiming</code> interface.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/navigation-timing/">Navigation Timing</a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds the <code>PerformanceTiming</code> and <code>PerformanceNavigation</code> interfaces. Adds <code>timing</code> and <code>navigation</code> properties to the <code>Performance</code> interface.</td></tr><tr class="even"><td><a href="https://w3c.github.io/navigation-timing/">Navigation Timing Level 2</a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds the <code>PerformanceNavigationTiming</code> interface. Obsolete's the <code>PerformanceTiming</code> interface, the <code>PerformanceNavigation</code> interface, as well as the <code>timing</code> and <code>navigation</code> properties to the <code>Performance</code> interface.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/performance-timeline/">Performance Timeline</a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds the <code>PerformanceEntry</code> interface, the <code>PerformanceEntryList</code> type, as well as the <code>getEntries()</code>, <code>getEntriesByType()</code>, and <code>getEntriesByName()</code> methods on the <code>Performance</code> interface.</td></tr><tr class="even"><td><a href="https://w3c.github.io/performance-timeline/">Performance Timeline Level 2</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds serializer to the <code>PerformanceEntry</code> interface as well as adding the <code>PerformanceObserver</code> interface and callback</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/resource-timing-1/">Resource Timing Level 1</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds the <code>PerformanceResourceTiming</code> interface. Adds the <code>clearResourceTimings()</code> method, the <code>setResourceTimingBufferSize()</code> method, and the <code>onresourcetimingbufferfull</code> event handler to the <code>Performance</code> interface. Also adds the <code>Timing-Allow-Origin</code> response header.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/resource-timing-2/">Resource Timing Level 2</a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds the <code>nextHopProtocol</code>, <code>workerStart</code>, <code>transferSize</code>, <code>encodedBodySize</code>, and <code>decodedBodySize</code> properties to the <code>PerformanceResourceTiming</code> interface.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/resource-timing/">Resource Timing Level 3</a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/user-timing/">User Timing</a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds <code>mark()</code>, <code>clearMarks()</code>, <code>measure()</code> and <code>clearMeasures()</code> methods to the <code>Performance</code> interface. Adds the <code>PerformanceMark</code> and <code>PeformanceMeasure</code> interfaces.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/user-timing/">User Timing Level 2</a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

## Implementation status

As shown in the [`Performance`](performance) interface's [Browser Compatibility](performance#browser_compatibility) table, most of these interfaces are broadly implemented by desktop browsers.

To test your browser's support for the [`Performance`](performance) interface, run the `perf-api-support` application.

## See also

- [A Primer for Web Performance Timing APIs](https://w3c.github.io/perf-timing-primer/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance_API</a>
