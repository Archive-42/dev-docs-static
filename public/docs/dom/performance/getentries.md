performance.getEntries()
========================

The `getEntries()` method returns a list of all [`PerformanceEntry`](../performanceentry) objects for the page. The list's members (*entries*) can be created by making performance *marks* or *measures* (for example by calling the [`mark()`](mark) method) at explicit points in time. If you are only interested in performance entries of certain types or that have certain names, see [`getEntriesByType()`](getentriesbytype) and [`getEntriesByName()`](getentriesbyname).

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

General syntax:

    entries = window.performance.getEntries();

### Return value

entries  
An array of [`PerformanceEntry`](../performanceentry) objects. The items will be in chronological order based on the entries' [`startTime`](../performanceentry/starttime).

Example
-------

    function use_PerformanceEntry_methods() {
      console.log("PerformanceEntry tests ...");

      if (performance.mark === undefined) {
        console.log("... performance.mark Not supported");
        return;
      }

      // Create some performance entries via the mark() method
      performance.mark("Begin");
      do_work(50000);
      performance.mark("End");
      performance.mark("Begin");
      do_work(100000);
      performance.mark("End");
      do_work(200000);
      performance.mark("End");

      // Use getEntries() to iterate through the each entry
      let p = performance.getEntries();
      for (var i=0; i < p.length; i++) {
        console.log("Entry[" + i + "]");
        check_PerformanceEntry(p[i]);
      }

      // Use getEntriesByType() to get all "mark" entries
      p = performance.getEntriesByType("mark");
      for (let i=0; i < p.length; i++) {
        console.log ("Mark only entry[" + i + "]: name = " + p[i].name +
             "; startTime = " + p[i].startTime +
             "; duration  = " + p[i].duration);
      }

      // Use getEntriesByName() to get all "mark" entries named "Begin"
      p = performance.getEntriesByName("Begin", "mark");
      for (let i=0; i < p.length; i++) {
        console.log ("Mark and Begin entry[" + i + "]: name = " + p[i].name +
             "; startTime = " + p[i].startTime +
             "; duration  = " + p[i].duration);
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#dom-performance-getentries">Performance Timeline Level 2<br />
<span class="small">The definition of 'getEntries()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/performance-timeline/#dom-performance-getentries">Performance Timeline<br />
<span class="small">The definition of 'getEntries()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance/getEntries" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance/getEntries</a>
