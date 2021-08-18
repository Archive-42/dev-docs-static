VideoTrack.selected
===================

The **[`VideoTrack`](../videotrack)** property `selected` controls whether or not a particular video track is active.

Syntax
------

    isVideoSelected = VideoTrack.selected;

    VideoTrack.selected = true | false;

### Value

The `selected` property is a Boolean whose value is `true` if the track is active. Only a single video track can be active at any given time, so setting this property to `true` for one track while another track is active will make that other track inactive.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-videotrack-selected">HTML Living Standard<br />
<span class="small">The definition of 'VideoTrack: selected' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`selected`

37

79

12-79

33

10

24

6.1

No

37

33

24

7

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoTrack/selected" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoTrack/selected</a>
