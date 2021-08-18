Performance: resourcetimingbufferfull event
===========================================

The `resourcetimingbufferfull` event is fired when the browser's [resource timing buffer](setresourcetimingbuffersize) is full.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onresourcetimingbufferfull"><code>onresourcetimingbufferfull</code></a></td></tr></tbody></table>

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

Note that you could also set up the handler using the addEventListener() function:

    performance.addEventListener('resourcetimingbufferfull', buffer_full);

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

`resourcetimingbufferfull_event`

46

22-57

≤79

Yes

No

No

11

46

≤37-57

46

25-57

Yes

Yes

No

5.0

1.5-7.0

See also
--------

-   [`Performance.clearResourceTimings()`](clearresourcetimings)
-   [`Performance.setResourceTimingBufferSize()`](setresourcetimingbuffersize)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance/resourcetimingbufferfull_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance/resourcetimingbufferfull_event</a>
