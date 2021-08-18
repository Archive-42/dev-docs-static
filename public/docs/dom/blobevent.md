# BlobEvent

The `BlobEvent` interface represents events associated with a [`Blob`](blob). These blobs are typically, but not necessarily, associated with media content.

## Constructor

[`BlobEvent()`](blobevent/blobevent)  
Creates a `BlobEvent` event with the given parameters.

## Properties

_Inherits properties from its parent [`Event`](event)_.

[`BlobEvent.data`](blobevent/data) <span class="badge inline readonly">Read only </span>  
A [`Blob`](blob) representing the data associated with the event. The event was fired on the [`EventTarget`](eventtarget) because of something happening on that specific [`Blob`](blob).

[`BlobEvent.timecode`](blobevent/timecode) <span class="badge inline readonly">Read only </span>  
A [`DOMHighResTimeStamp`](domhighrestimestamp) indicating the difference between the timestamp of the first chunk in data and the timestamp of the first chunk in the first BlobEvent produced by this recorder. Note that the timecode in the first produced BlobEvent does not need to be zero.

## Methods

_No specific method; inherits methods from its parent [`Event`](event)._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-record/#blobevent-section">MediaStream Recording<br />
<span class="small">The definition of 'BlobEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`BlobEvent`

49

≤79

22

No

36

14

49

49

22

36

14

5.0

`BlobEvent`

49

≤79

22

No

36

14

49

49

22

36

14

5.0

`data`

49

≤79

22

No

36

No

49

49

22

36

No

5.0

`timecode`

57

≤79

?

No

44

14

57

57

?

43

14

7.0

## See also

- The [`Event`](event) base interface.
- [MediaStream Recording API](mediastream_recording_api): Sends `BlobEvent` objects each time a chunk of media is ready.
- [Using the MediaStream Recording API](mediastream_recording_api/using_the_mediastream_recording_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BlobEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BlobEvent</a>
