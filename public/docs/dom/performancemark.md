PerformanceMark
===============

`PerformanceMark` is an *abstract* interface for [`PerformanceEntry`](performanceentry) objects with an [`entryType`](performanceentry/entrytype) of "`mark`". Entries of this type are created by calling [`performance.mark()`](performance/mark) to add a *named* [`DOMHighResTimeStamp`](domhighrestimestamp) (the *mark*) to the browser's *performance timeline*.

**Note:** This feature is available in [Web Workers](web_workers_api).

Properties
----------

This interface has no properties but it extends the following [`PerformanceEntry`](performanceentry) properties by qualifying/constraining the properties as follows:

[`PerformanceEntry.entryType`](performanceentry/entrytype)  
Returns "`mark`".

[`PerformanceEntry.name`](performanceentry/name)  
Returns the name given to the mark when it was created via a call to [`performance.mark()`](performance/mark).

[`PerformanceEntry.startTime`](performanceentry/starttime)  
Returns the [`DOMHighResTimeStamp`](domhighrestimestamp) when [`performance.mark()`](performance/mark) was called.

[`PerformanceEntry.duration`](performanceentry/duration)  
Returns "`0`". (A mark has no *duration*.)

Methods
-------

This interface has no methods.

Example
-------

See the example in [Using the User Timing API](user_timing_api/using_the_user_timing_api).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/user-timing/#performancemark">User Timing Level 2<br />
<span class="small">The definition of 'PerformanceMark' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/user-timing/#performancemark">User Timing<br />
<span class="small">The definition of 'PerformanceMark' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Basic definition.</td></tr></tbody></table>

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

`PerformanceMark`

43

12

41

10

33

11

43

43

42

33

11

4.0

`PerformanceMark`

76

79

No

No

63

14.1

79

76

No

54

14.5

12.0

`detail`

76

79

No

No

63

14.1

79

76

No

54

14.5

12.0

See also
--------

-   [User Timing (Overview)](user_timing_api)
-   [Using the User Timing API](user_timing_api/using_the_user_timing_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceMark" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceMark</a>
