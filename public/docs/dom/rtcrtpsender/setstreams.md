RTCRtpSender.setStreams()
=========================

The [`RTCRtpSender`](../rtcrtpsender) method `setStreams()` associates the sender's [`track`](track) with the specified [`MediaStream`](../mediastream) or array of `MediaStream` objects.

Syntax
------

    rtcRtpSender.setStreams(mediaStream);
    rtcRtpSender.setStreams([mediaStream...]);

### Parameters

 `mediaStream` or `[mediaStream...]` <span class="badge inline optional">Optional</span>   
An [`MediaStream`](../mediastream) object—or an array of multiple `MediaStream` objects—identifying the streams to which the `RTCRtpSender`'s [`track`](track) belongs. If this parameter isn't specified, no new streams will be associated with the track.

### Return value

None.

### Exceptions

`InvalidStateError`  
The sender's connection is closed.

Description
-----------

`setStreams()` is purely additive. It doesn't remove the track from any streams; it adds it to new ones. If you specify streams to which the track already belongs, that stream is unaffected.

Once the track has been added to all of the streams, renegotiation of the connection will be triggered by the [`negotiationneeded`](../rtcpeerconnection/negotiationneeded_event) event being dispatched to the [`RTCPeerConnection`](../rtcpeerconnection) to which the sender belongs.

Example
-------

This example adds all of an [`RTCPeerConnection`](../rtcpeerconnection)'s tracks to the specified stream.

    function addTracksToStream(stream) {
      let senders = pc.getSenders();

      senders.forEach((sender) => {
        if (sender.track && (sender.transport.state === connected)) {
          sender.setStreams(stream);
        }
      });
    }

After calling the [`RTCPeerConnection`](../rtcpeerconnection) method [`getSenders()`](../rtcpeerconnection/getsenders) to get the list of the connection's senders, the `addTracksToStream()` function iterates over the list. For each sender, if the sender's track is non-null and its transport's state is `connected`, we call `setStreams()` to add the track to the `stream` specified.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcrtpsender-setstreams">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCRtpSender.setStreams()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`setStreams`

76

79

No

No

63

14.1

79

76

No

54

14.5

12.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/setStreams" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCRtpSender/setStreams</a>
