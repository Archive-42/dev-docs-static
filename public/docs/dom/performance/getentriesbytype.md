# performance.getEntriesByType()

The `getEntriesByType()` method returns a list of [`PerformanceEntry`](../performanceentry) objects for a given _type_. The list's members (_entries_) can be created by making performance _marks_ or _measures_ (for example by calling the [`mark()`](mark) method) at explicit points in time.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    entries = window.performance.getEntriesByType(type);

### Arguments

type  
The type of entry to retrieve such as "`mark`". The valid entry types are listed in [`PerformanceEntry.entryType`](../performanceentry/entrytype).

### Return value

entries  
A list of [`PerformanceEntry`](../performanceentry) objects that have the specified `type`. The items will be in chronological order based on the entries' [`startTime`](../performanceentry/starttime). If no objects have the specified `type`, or no argument is provided, an empty list is returned.

## Example

    function usePerformanceEntryMethods() {
      log("PerformanceEntry tests ...");

      if (performance.mark === undefined) {
        log("... performance.mark Not supported");
        return;
      }

      // Create some performance entries via the mark() method
      performance.mark("Begin");
      doWork(50000);
      performance.mark("End");
      performance.mark("Begin");
      doWork(100000);
      performance.mark("End");
      doWork(200000);
      performance.mark("End");

      // Use getEntries() to iterate through the each entry
      var p = performance.getEntries();
      for (var i=0; i < p.length; i++) {
        log("Entry[" + i + "]");
        checkPerformanceEntry(p[i]);
      }

      // Use getEntries(name, entryType) to get specific entries
      p = performance.getEntries({name : "Begin", entryType: "mark"});
      for (var i=0; i < p.length; i++) {
        log("Begin[" + i + "]");
        checkPerformanceEntry(p[i]);
      }

      // Use getEntriesByType() to get all "mark" entries
      p = performance.getEntriesByType("mark");
      for (var i=0; i < p.length; i++) {
        log ("Mark only entry[" + i + "]: name = " + p[i].name +
             "; startTime = " + p[i].startTime +
             "; duration  = " + p[i].duration);
      }

      // Use getEntriesByName() to get all "mark" entries named "Begin"
      p = performance.getEntriesByName("Begin", "mark");
      for (var i=0; i < p.length; i++) {
        log ("Mark and Begin entry[" + i + "]: name = " + p[i].name +
             "; startTime = " + p[i].startTime +
             "; duration  = " + p[i].duration);
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#dom-performance-getentriesbytype">Performance Timeline Level 2<br />
<span class="small">The definition of 'getEntriesByType()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/performance-timeline/#dom-performance-getentriesbytype">Performance Timeline<br />
<span class="small">The definition of 'getEntriesByType()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance/getEntriesByType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance/getEntriesByType</a>
