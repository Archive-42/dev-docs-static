# performance.measure()

The `measure()` method creates a named [`timestamp`](../domhighrestimestamp) in the browser's _performance entry buffer_ between marks, the navigation start time, or the current time. When measuring between two marks, there is a _start mark_ and _end mark_, respectively. The named timestamp is referred to as a _measure_.

The `measure` can be retrieved by one of the [`Performance`](../performance) interfaces: ([`getEntries()`](getentries), [`getEntriesByName()`](getentriesbyname) or [`getEntriesByType()`](getentriesbytype)).

The `measure`'s [`performance entry`](../performanceentry) will have the following property values:

- [`entryType`](../performanceentry/entrytype) - set to "`measure`".
- [`name`](../performanceentry/name) - set to the "`name`" given when the measure was created.
- [`startTime`](../performanceentry/starttime) - set to the start mark [`timestamp`](../domhighrestimestamp).
- [`duration`](../performanceentry/duration) - set to a [`DOMHighResTimeStamp`](../domhighrestimestamp) that is the duration of the measure (typically, the end mark timestamp minus the start mark timestamp).

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    performance.measure(name);
    performance.measure(name, startMark);
    performance.measure(name, startMark, endMark);
    performance.measure(name, undefined, endMark);

### Arguments

name  
A [`DOMString`](../domstring) representing the name of the measure.

startMark <span class="badge inline optional">Optional</span>  
A [`DOMString`](../domstring) representing the name of the measure's starting mark. May also be the name of a [`PerformanceTiming`](../performancetiming) property. If it is omitted, then the start time will be the navigation start time.

endMark <span class="badge inline optional">Optional</span>  
A [`DOMString`](../domstring) representing the name of the measure's ending mark. May also be the name of a [`PerformanceTiming`](../performancetiming) property. If it is omitted, then the current time is used.

### Return value

void

## Example

The following example shows how `measure()` is used to create a new _measure_ [`performance entry`](../performanceentry) in the browser's performance entry buffer.

    const markerNameA = "example-marker-a"
    const markerNameB = "example-marker-b"

    // Run some nested timeouts, and create a PerformanceMark for each.
    performance.mark(markerNameA);
    setTimeout(function() {
      performance.mark(markerNameB);
      setTimeout(function() {

        // Create a variety of measurements.
        performance.measure("measure a to b", markerNameA, markerNameB);
        performance.measure("measure a to now", markerNameA);
        performance.measure("measure from navigation start to b", undefined, markerNameB);
        performance.measure("measure from navigation start to now");

        // Pull out all of the measurements.
        console.log(performance.getEntriesByType("measure"));

        // Finally, clean up the entries.
        performance.clearMarks();
        performance.clearMeasures();
      }, 1000);
    }, 1000);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/user-timing/#dom-performance-measure">User Timing Level 2<br />
<span class="small">The definition of 'measure()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Clarifies <code>measure()</code> processing model.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/user-timing/#dom-performance-measure">User Timing<br />
<span class="small">The definition of 'measure()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Basic definition.</td></tr></tbody></table>

## Browser compatibility

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance/measure" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance/measure</a>
