RTCRtpSender.replaceTrack()
===========================

The [`RTCRtpSender`](../rtcrtpsender) method `replaceTrack()` replaces the track currently being used as the sender's source with a new [`MediaStreamTrack`](../mediastreamtrack). The new track must be of the same media kind (audio, video, etc) and switching the track should not require negotiation.

Among the use cases for `replaceTrack()` is the common need to switch between the rear- and front-facing cameras on a phone. With `replaceTrack()`, you can have a track object for each camera and switch between the two as needed. See the example [Switching cameras](#switching_cameras) below.

Syntax
------

    trackReplacedPromise = sender.replaceTrack(newTrack);

### Parameters

 `newTrack` <span class="badge inline optional">Optional</span>   
A [`MediaStreamTrack`](../mediastreamtrack) specifying the track with which to replace the `RTCRtpSender`'s current source track. The new track's [`kind`](../mediastreamtrack/kind) must be the same as the current track's, or the replace track request will fail.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled once the track has been successfully replaced. The promise is rejected if the track cannot be replaced for any reason; this is commonly because the change would require renegotiation of the codec, which is not allowed (see [Things that require negotiation](#things_that_require_negotiation)).

If `newTrack` was omitted or was `null`, `replaceTrack()` stops the sender. No negotiation is required in this case.

When the promise is fulfilled, the fulfillment handler receives a value of `undefined`.

### Exceptions

If the returned promise is rejected, one of the following exceptions is provided to the rejection handler:

`InvalidModificationError`  
Replacing the `RTCRtpSender`'s current track with the new one would require negotiation.

`InvalidStateError`  
The track on which this method was called is stopped rather than running.

`TypeError`  
The new track's `kind` doesn't match the original track.

Usage notes
-----------

### Things that trigger negotiation

Not all track replacements require renegotiation. In fact, even changes that seem huge can be done without requiring negotation. Here are the changes that can trigger negotiaton:

-   The new track has a resolution which is outside the bounds of the current track; that is, the new track is either wider or taller than the current one.
-   The new track's frame rate is high enough to cause the codec's block rate to be exceeded.
-   The new track is a video track and its raw or pre-encoded state differs from that of the original track.
-   The new track is an audio track with a different number of channels fom the original.
-   Media sources that have built-in encoders — such as hardware encoders — may not be able to provide the negotiated codec. Software sources may not implement the negotiated codec.

Examples
--------

### Switching video cameras

    // example to change video camera, suppose selected value saved into window.selectedCamera

    navigator.mediaDevices
      .getUserMedia({
        video: {
          deviceId: {
            exact: window.selectedCamera
          }
        }
      })
      .then(function(stream) {
        let videoTrack = stream.getVideoTracks()[0];
        PCs.forEach(function(pc) {
          var sender = pc.getSenders().find(function(s) {
            return s.track.kind == videoTrack.kind;
          });
          console.log('found sender:', sender);
          sender.replaceTrack(videoTrack);
        });
      })
      .catch(function(err) {
        console.error('Error happens:', err);
      });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpsender-replacetrack">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpSender.replaceTrack()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`replaceTrack`

65

≤18

Yes

No

52

11

65

65

Yes

47

11

9.0

See also
--------

-   [WebRTC API](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/replaceTrack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/replaceTrack</a>
