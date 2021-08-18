MediaStreamTrack.muted
======================

The `muted` read-only property of the [`MediaStreamTrack`](../mediastreamtrack) interface returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating whether or not the track is currently unable to provide media output.

To implement a way for users to mute and unmute a track, use the [`enabled`](enabled) property. When a track is disabled by setting `enabled` to `false`, it generates only empty frames (audio frames in which every sample is 0, or video frames in which every pixel is black).

Syntax
------

    const mutedFlag = track.muted

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) which is `true` if the track is currently muted, or `false` if the track is currently unmuted.

When possible, avoid polling `muted` to monitor the track's muting status. Instead, add event listeners for the `mute` and `unmute` events.

Example
-------

This example counts the number of tracks in an array of [`MediaStreamTrack`](../mediastreamtrack) objects which are currently muted.

    let mutedCount = 0;

    trackList.forEach((track) => {
      if (track.muted) {
        mutedCount += 1;
      }
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-main/#dom-mediastreamtrack-muted">Media Capture and Streams<br />
<span class="small">The definition of 'muted' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`muted`

Yes

12

59

No

Yes

11

Yes

Yes

59

Yes

11

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/muted" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamTrack/muted</a>
