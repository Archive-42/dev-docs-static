VTTCue()
========

The `VTTCue()` constructor creates and returns a new [`VTTCue`](../vttcue) object.

Syntax
------

     vttCue = new VTTCue(startTime, endTime, text);

### Parameters

`startTime`  
This is a `double` representing the initial text track cue start time. This is the time, given in seconds and fractions of a second, denoting the beginning of the range of the media data to which this cue applies. For example, if a cue is to be visible from 50 seconds to a one minute, five and a half seconds in the media's playback, `startTime` will be 50.0.

`endTime`  
This is a `double` representing the ending time for this text track cue. This is the time at which the cue should stop being presented to the user, given in seconds and fractions thereof. Given the example cue mentioned under `startTime`, the value of `endTime` would be 65.5.

`text`  
A [`DOMString`](../domstring) providing the text that will be shown during the time span indicated by `startTime` and `endTime`.

### Return value

A new [`VTTCue`](../vttcue) object representing a cue which will be presented during the time span given.

Example
-------

    // Create a cue that is shown from 2 to 3 seconds and uses the given text.
    var cue = new VTTCue(2, 3, 'Cool text to be displayed');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webvtt/#dom-vttcue-vttcue">WebVTT: The Web Video Text Tracks Format<br />
<span class="small">The definition of 'VTTCue()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`VTTCue`

33

≤79

Yes

No

20

6.1

4.4.3

33

Yes

20

8

2.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VTTCue/VTTCue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VTTCue/VTTCue</a>
