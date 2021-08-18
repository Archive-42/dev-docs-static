VTTRegion
=========

The `VTTRegion` interface—part of the API for handling WebVTT (text tracks on media presentations)—describes a portion of the video to render a [`VTTCue`](vttcue) onto.

Constructor
-----------

<span class="page-not-created">`VTTRegion()`</span>  
Returns a newly created `VTTRegion` object.

Properties
----------

<span class="page-not-created">`VTTRegion.id`</span>  
A [`DOMString`](domstring) that identifies the region.

<span class="page-not-created">`VTTRegion.width`</span>  
A `double` representing the width of the region, as a percentage of the video.

<span class="page-not-created">`VTTRegion.lines`</span>  
A `double` representing the height of the region, in number of lines.

<span class="page-not-created">`VTTRegion.regionAnchorX`</span>  
A `double` representing the region anchor X offset, as a percentage of the region.

<span class="page-not-created">`VTTRegion.regionAnchorY`</span>  
A `double` representing the region anchor Y offset, as a percentage of the region.

<span class="page-not-created">`VTTRegion.viewportAnchorX`</span>  
A `double` representing the viewport anchor X offset, as a percentage of the video.

<span class="page-not-created">`VTTRegion.viewportAnchorY`</span>  
A `double` representing the viewport anchor Y offset, as a percentage of the video.

<span class="page-not-created">`VTTRegion.scroll`</span>  
An enum representing how adding new cues will move existing cues.

Examples
--------

    var region = new VTTRegion();
    region.width = 50;  // Use 50% of the video width
    region.lines = 4;  // Use 4 lines of height.
    region.viewportAnchorX = 25;  // Have the region start at 25% from the left.
    var cue = new VTTCue(2, 3, 'Cool text to be displayed');
    cue.region = region;  // This cue will be drawn only within this region.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webvtt/">WebVTT: The Web Video Text Tracks Format</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`VTTRegion`

No

No

59

No

No

7

No

No

59

No

7

No

`VTTRegion`

No

No

59

No

No

7

No

No

59

No

7

No

`id`

No

No

59

No

No

7

No

No

59

No

7

No

`lines`

No

No

59

No

No

12.1

No

No

59

No

12.2

No

`regionAnchorX`

No

No

59

No

No

7

No

No

59

No

7

No

`regionAnchorY`

No

No

59

No

No

7

No

No

59

No

7

No

`scroll`

No

No

59

No

No

7

No

No

59

No

7

No

`viewportAnchorX`

No

No

59

No

No

7

No

No

59

No

7

No

`viewportAnchorY`

No

No

59

No

No

7

No

No

59

No

7

No

`width`

No

No

59

No

No

7

No

No

59

No

7

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VTTRegion" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VTTRegion</a>
