performance.clearResourceTimings()
==================================

The `clearResourceTimings()` method removes all [`performance entries`](../performanceentry) with an [`entryType`](../performanceentry/entrytype) of "`resource`" from the browser's performance data buffer and sets the size of the performance data buffer to zero. To set the size of the browser's performance data buffer, use the [`Performance.setResourceTimingBufferSize()`](setresourcetimingbuffersize) method.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    performance.clearResourceTimings();

### Arguments

void

### Return value

none  
This method has no return value.

Example
-------

    function load_resource() {
      var image = new Image();
      image.src = "https://developer.mozilla.org/static/img/opengraph-logo.png";
    }
    function clear_performance_timings() {
      if (performance === undefined) {
        log("Browser does not support Web Performance");
        return;
      }
      // Create a resource timing performance entry by loading an image
      load_resource();

      var supported = typeof performance.clearResourceTimings == "function";
      if (supported) {
        console.log("Run: performance.clearResourceTimings()");
        performance.clearResourceTimings();
      } else {
        console.log("performance.clearResourceTimings() NOT supported");
        return;
      }
      // getEntries should now return zero
      var p = performance.getEntriesByType("resource");
      if (p.length == 0)
        console.log("... Performance data buffer cleared");
      else
        console.log("... Performance data buffer NOT cleared!");
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/resource-timing-1/#dom-performance-clearresourcetimings">Resource Timing Level 1<br />
<span class="small">The definition of 'clearResourceTimings()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance/clearResourceTimings" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance/clearResourceTimings</a>
