Performance.onresourcetimingbufferfull
======================================

The `onresourcetimingbufferfull` property is an event handler that will be called when the `resourcetimingbufferfull` event is fired. This event is fired when the browser's resource timing performance buffer is full.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    callback = performance.onresourcetimingbufferfull = buffer_full_cb;

### Return value

callback  
An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that is invoked when the `resourcetimingbufferfull` event is fired.

Examples
--------

The following example sets a callback function on the `onresourcetimingbufferfull` property.

    function buffer_full(event) {
      console.log("WARNING: Resource Timing Buffer is FULL!");
      performance.setResourceTimingBufferSize(200);
    }
    function init() {
      // Set a callback if the resource buffer becomes filled
      performance.onresourcetimingbufferfull = buffer_full;
    }
    <body onload="init()">

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/resource-timing-1/#dom-performance-onresourcetimingbufferfull">Resource Timing Level 1<br />
<span class="small">The definition of 'onresourcetimingbufferfull' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onresourcetimingbufferfull`

46

22-57

≤79

35

No

No

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

See also
--------

-   `resourcetimingbufferfull` event
-   [`Performance.clearResourceTimings()`](clearresourcetimings)
-   [`Performance.setResourceTimingBufferSize()`](setresourcetimingbuffersize)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance/onresourcetimingbufferfull" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance/onresourcetimingbufferfull</a>
