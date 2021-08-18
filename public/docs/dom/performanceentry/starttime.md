# PerformanceEntry.startTime

The `startTime` property returns the first recorded [`timestamp`](../domhighrestimestamp) of the [`performance entry`](../performanceentry).

**Note:** This feature is available in [Web Workers](../web_workers_api).

The value returned by this property depends on the performance entry's [`type`](entrytype):

- "`frame`" - returns the [`timestamp`](../domhighrestimestamp) when the frame was started.
- "`mark`" - returns the [`timestamp`](../domhighrestimestamp) when the mark was created by a call to [`performance.mark()`](../performance/mark).
- "`measure`" - returns the [`timestamp`](../domhighrestimestamp) when the measure was created by a call to [`performance.measure()`](../performance/measure).
- "`navigation`" - returns the [`timestamp`](../domhighrestimestamp) with a value of "`0`".
- "`resource`" - returns the [`timestamp`](../domhighrestimestamp) immediately before the browser [`starts fetching the resource`](../performanceresourcetiming/fetchstart).

This property is <span class="badge inline readonly">Read only </span>.

## Syntax

    entry.startTime;

### Return value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) representing the first timestamp when the [`performance entry`](../performanceentry) was created.

Note: if the performance entry has an [`entryType`](entrytype) of "`resource`" (i.e. the entry is a [`PerformanceResourceTiming`](../performanceresourcetiming) object), this property returns the [`PerformanceResourceTiming.fetchStart`](../performanceresourcetiming/fetchstart) [`timestamp`](../domhighrestimestamp).

## Example

The following example shows the use of the `startTime` property.

    function run_PerformanceEntry() {
      log("PerformanceEntry support ...");

      if (performance.mark === undefined) {
        log("... performance.mark Not supported");
        return;
      }

      // Create some performance entries via the mark() method
      performance.mark("Begin");
      do_work(50000);
      performance.mark("End");

      // Use getEntries() to iterate through the each entry
      var p = performance.getEntries();
      for (var i=0; i < p.length; i++) {
        log("Entry[" + i + "]");
        check_PerformanceEntry(p[i]);
      }
    }
    function check_PerformanceEntry(obj) {
      var properties = ["name", "entryType", "startTime", "duration"];
      var methods = ["toJSON"];

      for (var i=0; i < properties.length; i++) {
        // check each property
        var supported = properties[i] in obj;
        if (supported)
          log("..." + properties[i] + " = " + obj[properties[i]]);
        else
          log("..." + properties[i] + " = Not supported");
      }
      for (var i=0; i < methods.length; i++) {
        // check each method
        var supported = typeof obj[methods[i]] == "function";
        if (supported) {
          var js = obj[methods[i]]();
          log("..." + methods[i] + "() = " + JSON.stringify(js));
        } else {
          log("..." + methods[i] + " = Not supported");
        }
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#dom-performanceentry-starttime">Performance Timeline Level 2<br />
<span class="small">The definition of 'startTime' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/performance-timeline/#dom-performanceentry-starttime">Performance Timeline<br />
<span class="small">The definition of 'startTime' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceEntry/startTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceEntry/startTime</a>
