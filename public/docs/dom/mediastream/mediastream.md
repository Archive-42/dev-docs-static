# MediaStream()

The `MediaStream()` constructor returns a newly-created [`MediaStream`](../mediastream), which serves as a collection of media tracks, each represented by a [`MediaStreamTrack`](../mediastreamtrack) object. If any parameters are given, the specified tracks are added to the new stream. Otherwise, the stream has no tracks.

## Syntax

    newStream = new MediaStream();
    newStream = new MediaStream(stream);
    newStream = new MediaStream(tracks[]);

### Parameters

`stream`  
A different [`MediaStream`](../mediastream) object whose tracks are added to the newly-created stream automatically. The tracks are not removed from the original stream, so they're shared by the two streams.

`tracks`  
An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of [`MediaStreamTrack`](../mediastreamtrack) objects, one for each track to add to the stream.

### Return value

A newly-created [`MediaStream`](../mediastream) object, either empty, or containing the tracks provided, if any.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#mediastream">Media Capture and Streams<br />
<span class="small">The definition of 'MediaStream' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`MediaStream`

21

12

44

No

42

11

37

25

42

No

11

6.0

## See also

- [`MediaStream`](../mediastream)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/MediaStream" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStream/MediaStream</a>
