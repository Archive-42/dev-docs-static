PerformanceEntry
================

The `PerformanceEntry` object encapsulates a single performance metric that is part of the *performance timeline*. A *performance entry* can be directly created by making a performance *[`mark`](performancemark)* or *[`measure`](performancemeasure)* (for example by calling the [`mark()`](performance/mark) method) at an explicit point in an application. Performance entries are also created in indirect ways such as loading a resource (such as an image).

`PerformanceEntry` instances will always be one of the following subtypes:

-   [`PerformanceMark`](performancemark)
-   [`PerformanceMeasure`](performancemeasure)
-   [`PerformanceFrameTiming`](performanceframetiming)
-   [`PerformanceNavigationTiming`](performancenavigationtiming)
-   [`PerformanceResourceTiming`](performanceresourcetiming)
-   [`PerformancePaintTiming`](performancepainttiming)

**Note:** This feature is available in [Web Workers](web_workers_api).

Properties
----------

 [`PerformanceEntry.name`](performanceentry/name) <span class="badge inline readonly">Read only </span>   
A value that further specifies the value returned by the [`PerformanceEntry.entryType`](performanceentry/entrytype) property. The value of both depends on the subtype. See property page for valid values.

 [`PerformanceEntry.entryType`](performanceentry/entrytype) <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) representing the type of performance metric such as, for example, "`mark`". See property page for valid values.

 [`PerformanceEntry.startTime`](performanceentry/starttime) <span class="badge inline readonly">Read only </span>   
A [`DOMHighResTimeStamp`](domhighrestimestamp) representing the starting time for the performance metric.

 [`PerformanceEntry.duration`](performanceentry/duration) <span class="badge inline readonly">Read only </span>   
A [`DOMHighResTimeStamp`](domhighrestimestamp) representing the time value of the duration of the performance event.

Methods
-------

[`PerformanceEntry.toJSON()`](performanceentry/tojson)  
Returns a JSON representation of the `PerformanceEntry` object.

Example
-------

The following example checks all `PerformanceEntry` properties to see if the browser supports them and if so, write their values to the console.

    function print_PerformanceEntries() {
      // Use getEntries() to get a list of all performance entries
      var p = performance.getEntries();
      for (var i=0; i < p.length; i++) {
        console.log("PerformanceEntry[" + i + "]");
        print_PerformanceEntry(p[i]);
      }
    }
    function print_PerformanceEntry(perfEntry) {
      var properties = ["name",
                        "entryType",
                        "startTime",
                        "duration"];

      for (var i=0; i < properties.length; i++) {
        // Check each property
        var supported = properties[i] in perfEntry;
        if (supported) {
          var value = perfEntry[properties[i]];
          console.log("... " + properties[i] + " = " + value);
        } else {
          console.log("... " + properties[i] + " is NOT supported");
        }
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/resource-timing/">Resource Timing Level 3</a></td><td><span class="spec-ed">Editor's Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/resource-timing-2/">Resource Timing Level 2</a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/resource-timing-1/">Resource Timing Level 1</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Adds the <a href="performanceresourcetiming"><code>PerformanceResourceTiming</code></a> interface and the <code>resource</code> value for <code>entryType</code>.</td></tr><tr class="even"><td><a href="https://w3c.github.io/navigation-timing/">Navigation Timing Level 2</a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/navigation-timing/">Navigation Timing</a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds the <a href="performancenavigationtiming"><code>PerformanceNavigationTiming</code></a> interface and the <code>navigation</code> value for <code>entryType</code>.</td></tr><tr class="even"><td><a href="https://w3c.github.io/user-timing/">User Timing Level 2</a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/user-timing/">User Timing</a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds the <a href="performancemark"><code>PerformanceMark</code></a> and <a href="performancemeasure"><code>PerformanceMeasure</code></a> interfaces as well as the <code>mark</code> and <code>measure</code> values for <code>entryType</code>.</td></tr><tr class="even"><td><a href="https://wicg.github.io/frame-timing/">Frame Timing</a></td><td><span class="spec-draft">Draft</span></td><td>Adds the <a href="performanceframetiming"><code>PerformanceFrameTiming</code></a> interface and the <code>frame</code> value for <code>entryType</code>.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#dom-performanceentry">Performance Timeline Level 2<br />
<span class="small">The definition of 'PerformanceEntry' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added <code>toJSON()</code> serializer method.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/performance-timeline/#dom-performanceentry">Performance Timeline<br />
<span class="small">The definition of 'PerformanceEntry' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`PerformanceEntry`

46

25

12

Yes

Yes

33

15

11

46

≤37

46

25

25

33

14

11

5.0

1.5

`duration`

28

12

Yes

Yes

15

11

≤37

28

25

14

11

1.5

`entryType`

28

12

Yes

Yes

15

11

≤37

28

25

14

11

1.5

`name`

28

12

Yes

Yes

15

11

≤37

28

25

14

11

1.5

`startTime`

28

12

Yes

Yes

15

11

≤37

28

25

14

11

1.5

`toJSON`

45

16

Yes

No

32

11

45

45

25

32

11

5.0

`worker_support`

62

≤79

60

?

49

?

62

62

60

46

?

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceEntry" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceEntry</a>
