TimeRanges.end()
================

Returns the time offset at which a specified time range ends.

Syntax
------

    endTime = TimeRanges.end(index)

### Parameters

-   `index` is the range number to return the ending time for.

### Exceptions

INDEX\_SIZE\_ERR  
A `DOMException` thrown if the specified index doesn't correspond to an existing range.

Example
-------

Given a video element with the ID "myVideo":

    var v = document.getElementById("myVideo");

    var buf = v.buffered;

    var numRanges = buf.length;

    if (buf.length == 1) {
      // only one range
      if (buf.start(0) == 0 && buf.end(0) == v.duration) {
        // The one range starts at the beginning and ends at
        // the end of the video, so the whole thing is loaded
      }
    }

This example looks at the time ranges and looks to see if the entire video has been loaded.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-timeranges-end">HTML Living Standard<br />
<span class="small">The definition of 'TimeRanges.end()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`end`

6

12

4

9

≤12.1

3.1

≤37

18

4

≤12.1

2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TimeRanges/end" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TimeRanges/end</a>
