# performance.clearMeasures()

The `clearMeasures()` method removes the _named measure_ from the browser's performance entry buffer. If the method is called with no arguments, all [`performance entries`](../performanceentry) with an [`entry type`](../performanceentry/entrytype) of "`measure`" will be removed from the performance entry buffer.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    performance.clearMeasures();
    performance.clearMeasures(name);

### Arguments

name <span class="badge inline optional">Optional</span>  
A [`DOMString`](../domstring) representing the name of the timestamp. If this argument is omitted, all [`performance entries`](../performanceentry) with an [`entry type`](../performanceentry/entrytype) of "`measure`" will be removed.

### Return value

void

## Example

The following example shows both uses of the `clearMeasures()` method.

    // Create a small helper to show how many PerformanceMeasure entries there are.
    function logMeasureCount() {
      console.log(
        "Found this many entries: " + performance.getEntriesByType("measure").length
      );
    }

    // Create a bunch of measures.
    performance.measure("from navigation");
    performance.mark("a");
    performance.measure("from mark a", "a");
    performance.measure("from navigation");
    performance.measure("from mark a", "a");
    performance.mark("b");
    performance.measure("between a and b", "a", "b");

    logMeasureCount() // "Found this many entries: 5"

    // Delete just the "from navigation" PerformanceMeasure entries.
    performance.clearMeasures("from navigation");
    logMeasureCount() // "Found this many entries: 3"

    // Delete all of the PerformanceMeasure entries.
    performance.clearMeasures();
    logMeasureCount() // "Found this many entries: 0"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/user-timing/#dom-performance-clearmeasures">User Timing Level 2<br />
<span class="small">The definition of 'clearMeasures()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Clarifies <code>clearMeasures()</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/user-timing/#dom-performance-clearmeasures">User Timing<br />
<span class="small">The definition of 'clearMeasures()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Basic definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance/clearMeasures" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance/clearMeasures</a>
