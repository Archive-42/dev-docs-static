# PerformanceEntry.duration

The `duration` property returns a [`timestamp`](../domhighrestimestamp) that is the duration of the [`performance entry`](../performanceentry).

**Note:** This feature is available in [Web Workers](../web_workers_api).

The value returned by this property depends on the performance entry's [`type`](entrytype):

- "`frame`" - returns a [`timestamp`](../domhighrestimestamp) indicating the difference between the `startTime`s of two successive frames.
- "`mark`" - returns "`0`" (a mark has no duration).
- "`measure`" - returns the [`timestamp`](../domhighrestimestamp) that is the duration of the measure.
- "`navigation`" - returns the [`timestamp`](../domhighrestimestamp) that is the difference between the [`PerformanceNavigationTiming.loadEventEnd`](../performancenavigationtiming/loadeventend) and [`PerformanceEntry.startTime`](starttime) properties, respectively.
- "`resource`" - returns the difference between the resource's [`responseEnd`](../performanceresourcetiming/responseend) [`timestamp`](../domhighrestimestamp) and its [`startTime`](starttime) [`timestamp`](../domhighrestimestamp).

This property is <span class="badge inline readonly">Read only </span>.

## Syntax

    entry.duration;

### Return value

A [`DOMHighResTimeStamp`](../domhighrestimestamp) representing the duration of the [`performance entry`](../performanceentry). If the duration concept doesn't apply for a particular performance metric, the browser may choose to return a duration of 0.

Note: if the performance entry has an [`entryType`](entrytype) of "`resource`" (i.e. the entry is a [`PerformanceResourceTiming`](../performanceresourcetiming) object), this property returns the difference between the [`PerformanceResourceTiming.responseEnd`](../performanceresourcetiming/responseend) and [`PerformanceEntry.startTime`](starttime) [`timestamps`](../domhighrestimestamp).

## Example

The following example shows the use of the `duration` property.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#dom-performanceentry-duration">Performance Timeline Level 2<br />
<span class="small">The definition of 'duration' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/performance-timeline/#dom-performanceentry-duration">Performance Timeline<br />
<span class="small">The definition of 'duration' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceEntry/duration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceEntry/duration</a>
