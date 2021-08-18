# PerformanceObserver.takeRecords()

The `takeRecords()` method of the [`PerformanceObserver`](../performanceobserver) interface returns the current list of [`performance entries`](../performanceentry) stored in the performance observer, emptying it out.

## Syntax

    var performanceEntryList = performanceObserver.takeRecords();

### Parameters

None.

### Return value

A list of [`PerformanceEntry`](../performanceentry) objects.

## Example

    var observer = new PerformanceObserver(function(list, obj) {
      var entries = list.getEntries();
      for (var i=0; i < entries.length; i++) {
        // Process "mark" and "frame" events
      }
    });
    observer.observe({entryTypes: ["mark", "frame"]});
    var records = observer.takeRecords();
    console.log(records[0].name);
    console.log(records[0].startTime);
    console.log(records[0].duration);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/performance-timeline/#dom-performanceobserver-takerecords">Performance Timeline Level 2<br />
<span class="small">The definition of 'takeRecords()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition of <code>takeRecords()</code> method.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserver/takeRecords" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PerformanceObserver/takeRecords</a>
