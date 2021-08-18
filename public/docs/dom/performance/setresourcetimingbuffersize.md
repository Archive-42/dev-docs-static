# performance.setResourceTimingBufferSize()

The `setResourceTimingBufferSize()` method sets the browser's _resource timing buffer_ size to the specified number of "`resource`" [`performance entry type`](../performanceentry/entrytype) objects.

A browser's recommended resource timing buffer size is at least 150 [`performance entry`](../performanceentry) objects.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    performance.setResourceTimingBufferSize(maxSize);

### Arguments

maxSize  
A `number` representing the maximum number of [`performance entry`](../performanceentry) objects the browser should hold in its performance entry buffer.

### Return value

none  
This method has no return value.

## Example

    function setResourceTimingBufferSize(maxSize) {
      if (performance === undefined) {
        log("Browser does not support Web Performance");
        return;
      }
      var supported = typeof performance.setResourceTimingBufferSize == "function";
      if (supported) {
        log("... Performance.setResourceTimingBufferSize() = Yes");
        performance.setResourceTimingBufferSize(maxSize);
      } else {
        log("... Performance.setResourceTimingBufferSize() = NOT supported");
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/resource-timing-1/#dom-performance-setresourcetimingbuffersize">Resource Timing Level 1<br />
<span class="small">The definition of 'setResourceTimingBufferSize()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`setResourceTimingBufferSize`

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

No

5.0

1.5-7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance/setResourceTimingBufferSize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance/setResourceTimingBufferSize</a>
