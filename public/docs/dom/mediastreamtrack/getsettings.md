# MediaStreamTrack.getSettings()

The `getSettings()` method of the [`MediaStreamTrack`](../mediastreamtrack) interface returns a [`MediaTrackSettings`](../mediatracksettings) object containing the current values of each of the constrainable properties for the current `MediaStreamTrack`. See [Capabilities, constraints, and settings](../media_streams_api/constraints) for details on how to work with constrainable properties.

## Syntax

    const settings = track.getSettings()

### Returns

A [`MediaTrackSettings`](../mediatracksettings) object describing the current configuration of the track's constrainable properties.

**Note:** The returned object identifies the current values of every constrainable property, including those which are platform defaults rather than having been expressly set by the site's code. To instead fetch the most-recently established constraints for the track's properties, as specified by the site's code, use [`getConstraints()`](getconstraints).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastreamtrack-getsettings">Media Capture and Streams<br />
<span class="small">The definition of 'getSettings()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getSettings`

61

12

50

No

48

11

61

61

50

45

11

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getSettings" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/getSettings</a>
