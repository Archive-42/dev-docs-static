PerformanceObserver
===================

The `PerformanceObserver` interface is used to *observe* performance measurement events and be notified of new [performance entries](performanceentry) as they are recorded in the browser's *performance timeline*.

**Note:** This feature is available in [Web Workers](web_workers_api).

Constructor
-----------

[`PerformanceObserver()`](performanceobserver/performanceobserver)  
Creates and returns a new `PerformanceObserver` object.

Properties
----------

 [`PerformanceObserver.supportedEntryTypes`](performanceobserver/supportedentrytypes)<span class="badge inline readonly">Read only </span>   
Returns an array of the [`entryType`](performanceentry/entrytype) values supported by the user agent.

Methods
-------

[`PerformanceObserver.observe()`](performanceobserver/observe)  
Specifies the set of [`entry types`](performanceentry/entrytype) to observe. The performance observer's callback function will be invoked when a [`performance entry`](performanceentry) is recorded for one of the specified `entryTypes`

[`PerformanceObserver.disconnect()`](performanceobserver/disconnect)  
Stops the performance observer callback from receiving [`performance entries`](performanceentry).

[`PerformanceObserver.takeRecords()`](performanceobserver/takerecords)  
Returns the current list of [`performance entries`](performanceentry) stored in the performance observer, emptying it out.

Example
-------

    function observer_callback(list, observer) {
       // Process the "measure" event
    }
    let observer = new PerformanceObserver(observer_callback);
    observer.observe({entryTypes: ["measure"]});

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#dom-performanceobserver">Performance Timeline Level 2<br />
<span class="small">The definition of 'PerformanceObserver' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition of <code>PerformanceObserver</code> interface.</td></tr></tbody></table>

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

`PerformanceObserver`

52

≤79

57

No

39

11

52

52

57

41

11

6.0

`PerformanceObserver`

52

≤79

57

No

39

11

52

52

57

41

11

6.0

`disconnect`

52

≤79

57

No

39

11

52

52

57

41

11

6.0

`observe`

52

≤79

57

No

39

11

52

52

57

41

11

6.0

`supportedEntryTypes`

73

≤79

68

No

Yes

12.1

73

73

68

Yes

12.2

11.0

`takeRecords`

65

≤79

60

No

Yes

No

65

65

60

Yes

No

9.0

`worker_support`

62

≤79

?

No

49

?

62

62

?

46

?

8.0

See also
--------

-   [`MutationObserver`](mutationobserver)
-   [`ResizeObserver`](resizeobserver)
-   [`IntersectionObserver`](intersectionobserver)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserver</a>
