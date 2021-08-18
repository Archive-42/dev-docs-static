TimeRanges.length
=================

The `TimeRanges.length` read-only property returns the number of ranges in the object.

Syntax
------

    length = TimeRanges.length;

Example
-------

Given a video element with the ID "myVideo":

    var v = document.GetElementById("myVideo");

    var buf = v.buffered;

    var numRanges = buf.length;

    if (buf.length == 1) {
      // Only one range
      if (buf.start(0) == 0 && buf.end(0) == v.duration) {
        // The one range starts at the beginning and ends at
        // the end of the video, so the whole thing is loaded
      }
    }

This example looks at the time ranges and looks to see if the entire video has been loaded.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-timeranges-length">HTML Living Standard<br />
<span class="small">The definition of 'TimeRanges.length()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`length`

Yes

12

4

9

Yes

3.1

Yes

Yes

4

Yes

2

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TimeRanges/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TimeRanges/length</a>
