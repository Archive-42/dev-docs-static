PerformanceMeasure
==================

`PerformanceMeasure` is an *abstract* interface for [`PerformanceEntry`](performanceentry) objects with an [`entryType`](performanceentry/entrytype) of "`measure`". Entries of this type are created by calling [`performance.measure()`](performance/measure) to add a *named* [`DOMHighResTimeStamp`](domhighrestimestamp) (the *measure*) between two *marks* to the browser's *performance timeline*.

**Note:** This feature is available in [Web Workers](web_workers_api).

Properties
----------

This interface has no properties but it extends the following [`PerformanceEntry`](performanceentry) properties by qualifying/constrainting the properties as follows:

[`PerformanceEntry.entryType`](performanceentry/entrytype)  
Returns "`measure`".

[`PerformanceEntry.name`](performanceentry/name)  
Returns the name given to the measure when it was created via a call to [`performance.measure()`](performance/measure).

[`PerformanceEntry.startTime`](performanceentry/starttime)  
Returns a [`timestamp`](domhighrestimestamp) given to the measure when [`performance.measure()`](performance/measure) was called.

[`PerformanceEntry.duration`](performanceentry/duration)  
Returns a [`DOMHighResTimeStamp`](domhighrestimestamp) that is the duration of the measure (typically, the measure's end mark timestamp minus its start mark timestamp).

Methods
-------

This interface has no methods.

Example
-------

See the example in [Using the User Timing API](user_timing_api/using_the_user_timing_api).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/user-timing/#dom-performance-measure">User Timing Level 2<br />
<span class="small">The definition of 'PerformanceMeasure' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/user-timing/#performancemeasure">User Timing<br />
<span class="small">The definition of 'PerformanceMeasure' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Basic definition.</td></tr></tbody></table>

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

`PerformanceMeasure`

25

12

41

10

33

11

≤37

25

42

33

11

1.5

`detail`

78

79

No

No

65

14.1

78

78

No

56

14.5

12.0

See also
--------

-   [User Timing (Overview)](user_timing_api)
-   [Using the User Timing API](user_timing_api/using_the_user_timing_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceMeasure" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceMeasure</a>
