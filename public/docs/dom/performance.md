Performance
===========

The `Performance` interface provides access to performance-related information for the current page. It's part of the High Resolution Time API, but is enhanced by the [Performance Timeline API](performance_timeline), the [Navigation Timing API](navigation_timing_api), the [User Timing API](user_timing_api), and the [Resource Timing API](resource_timing_api).

An object of this type can be obtained by calling the [`window.performance`](window/performance) read-only attribute.

***Note*:** This interface and its members are available in [Web Workers](web_workers_api) via `WorkerGlobalScope.performance` , except where indicated below. Also, note that performance markers and measures are per context. If you create a mark on the main thread (or other worker), you cannot see it in a worker thread, and vice versa.

Properties
----------

*The `Performance` interface doesn't inherit any properties.*

 [`Performance.navigation`](performance/navigation) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A legacy [`PerformanceNavigation`](performancenavigation) object that provides useful context about the operations included in the times listed in `timing`, including whether the page was a load or a refresh, how many redirections occurred, and so forth.

Not available in workers.

 [`Performance.timing`](performance/timing) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
A legacy [`PerformanceTiming`](performancetiming) object containing latency-related performance information.

Not available in workers.

 [`Performance.memory`](performance/memory) <span class="badge inline readonly">Read only </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
A *non-standard* extension added in Chrome, this property provides an object with basic memory usage information. *You **should not use** this non-standard API.*

 [`Performance.timeOrigin`](performance/timeorigin) <span class="badge inline readonly">Read only </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the high resolution timestamp of the start time of the performance measurement.

Methods
-------

*The `Performance` interface doesn't inherit any methods.*

[`Performance.clearMarks()`](performance/clearmarks)  
Removes the given *mark* from the browser's performance entry buffer.

[`Performance.clearMeasures()`](performance/clearmeasures)  
Removes the given *measure* from the browser's performance entry buffer.

[`Performance.clearResourceTimings()`](performance/clearresourcetimings)  
Removes all [`performance entries`](performanceentry) with a [`entryType`](performanceentry/entrytype) of "`resource`" from the browser's performance data buffer.

[`Performance.getEntries()`](performance/getentries)  
Returns a list of [`PerformanceEntry`](performanceentry) objects based on the given *filter*.

[`Performance.getEntriesByName()`](performance/getentriesbyname)  
Returns a list of [`PerformanceEntry`](performanceentry) objects based on the given *name* and *entry type*.

[`Performance.getEntriesByType()`](performance/getentriesbytype)  
Returns a list of [`PerformanceEntry`](performanceentry) objects of the given *entry type*.

[`Performance.mark()`](performance/mark)  
Creates a [`timestamp`](domhighrestimestamp) in the browser's *performance entry buffer* with the given name.

[`Performance.measure()`](performance/measure)  
Creates a named [`timestamp`](domhighrestimestamp) in the browser's performance entry buffer between two specified marks (known as the *start mark* and *end mark*, respectively).

[`Performance.now()`](performance/now)  
Returns a [`DOMHighResTimeStamp`](domhighrestimestamp) representing the number of milliseconds elapsed since a reference instant.

[`Performance.setResourceTimingBufferSize()`](performance/setresourcetimingbuffersize)  
Sets the browser's resource timing buffer size to the specified number of "`resource`" [`type`](performanceentry/entrytype) [`performance entry`](performanceentry) objects.

[`Performance.toJSON()`](performance/tojson)  
Is a jsonizer returning a json object representing the `Performance` object.

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`resourcetimingbufferfull`](performance/resourcetimingbufferfull_event)  
Fired when the browser's [resource timing buffer](performance/setresourcetimingbuffersize) is full.  
Also available via the [`onresourcetimingbufferfull`](performance/onresourcetimingbufferfull) property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/hr-time-2/#sec-performance">High Resolution Time Level 2<br />
<span class="small">The definition of 'Performance' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines <code>toJson()</code> method.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/hr-time-1/#performance">High Resolution Time<br />
<span class="small">The definition of 'Performance' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines <code>now()</code> method.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#extensions-to-the-performance-interface">Performance Timeline Level 2<br />
<span class="small">The definition of 'Performance extensions' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Changes <code>getEntries()</code> interface.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/performance-timeline/#extensions-to-the-performance-interface">Performance Timeline<br />
<span class="small">The definition of 'Performance extensions' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines <code>getEntries()</code>, <code>getEntriesByType()</code> and <code>getEntriesByName()</code> methods.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/resource-timing-1/#extensions-performance-interface">Resource Timing Level 1<br />
<span class="small">The definition of 'Performance extensions' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defines <code>clearResourceTimings()</code> and <code>setResourceTimingBufferSize()</code> methods and the <code>onresourcetimingbufferfull</code> property.</td></tr><tr class="even"><td><a href="https://w3c.github.io/user-timing/#extensions-performance-interface">User Timing Level 2<br />
<span class="small">The definition of 'Performance extensions' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Clarifies <code>mark()</code>, <code>clearMark()</code>, <code>measure()</code> and <code>clearMeasure()</code> methods.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/user-timing/#extensions-performance-interface">User Timing<br />
<span class="small">The definition of 'Performance extensions' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Defines <code>mark()</code>, <code>clearMark()</code>, <code>measure()</code> and <code>clearMeasure()</code> methods.</td></tr></tbody></table>

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

`Performance`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`clearMarks`

29

25-29

12

41

10

33

11

≤37

29

25-29

42

33

11

2.0

1.5-2.0

`clearMeasures`

29

25-29

12

41

10

33

11

≤37

29

25-29

42

33

11

2.0

1.5-2.0

`clearResourceTimings`

46

22-57

12

35

10

Yes

11

46

≤37-57

46

25-57

35

Yes

11

5.0

1.5-7.0

`eventCounts`

85

85

No

No

71

No

85

85

No

60

No

14.0

`getEntries`

28

25-36

12

35

10

No

11

≤37

28

25-36

35

No

11

1.5

1.5-3.0

`getEntriesByName`

28

25-36

12

35

10

No

11

≤37

28

25-36

35

No

11

1.5

1.5-3.0

`getEntriesByType`

28

25-36

12

35

10

15

15-23

11

≤37

28

25-36

35

15

14-24

11

1.5

1.5-3.0

`mark`

28

25-28

12

41

10

33

11

≤37

28

25-28

42

33

11

1.5

`measure`

28

25-28

12

41

10

33

11

≤37

28

25-28

42

33

11

1.5

`memory`

7

≤79

No

No

Yes

No

≤37

18

No

Yes

No

1.0

`navigation`

10

12

7

9

15

8

≤37

18

7

No

9

1.0

`now`

24

21-24

12

15

\["In Firefox 57.0.4 the accuracy was reduced to 20 microseconds.", "In Firefox 59 the accuracy was reduced to 2 milliseconds.", "In Firefox 60 the accuracy was increased to 1 millisecond."\]

10

15

8

≤37

25

15

\["In Firefox 57.0.4 the accuracy was reduced to 20 microseconds.", "In Firefox 59 the accuracy was reduced to 2 milliseconds.", "In Firefox 60 the accuracy was increased to 1 millisecond."\]

14

9

1.5

`onresourcetimingbufferfull`

46

22-57

≤79

35

No

No

11

46

≤37-57

46

25-57

35

Yes

No

5.0

1.5-7.0

`resourcetimingbufferfull_event`

46

22-57

≤79

Yes

No

No

11

46

≤37-57

46

25-57

Yes

Yes

No

5.0

1.5-7.0

`setResourceTimingBufferSize`

46

22-57

12

35

10

Yes

11

46

≤37-57

46

25-57

35

Yes

No

5.0

1.5-7.0

`timeOrigin`

62

16

53

No

49

No

62

62

53

46

No

8.0

`timing`

6

12

7

9

15

8

≤37

18

7

14

9

1.0

`toJSON`

56

12

25

9

No

14.1

56

56

25

No

14.5

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance</a>
