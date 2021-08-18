RTCPeerConnection.getSenders()
==============================

The [`RTCPeerConnection`](../rtcpeerconnection) method `getSenders()` returns an array of [`RTCRtpSender`](../rtcrtpsender) objects, each of which represents the RTP sender responsible for transmitting one track's data. A sender object provides methods and properties for examining and controlling the encoding and transmission of the track's data.

Syntax
------

    var senders = rtcPeerConnection.getSenders();

### Return value

An array of [`RTCRtpSender`](../rtcrtpsender) objects, one for each track on the connection. The array is empty if there are no RTP senders on the connection.

The order of the returned `RTCRtpSender`s is not defined by the specification, and may change from one call to `getSenders()` to the next.

Example
-------

In this example, a `setMuting()` function is shown. This function takes as input an [`RTCPeerConnection`](../rtcpeerconnection), `pc`, and a Boolean, `muting`. The function gets the list of the peer connection's senders and iterates over every sender, setting the corresponding media track's [`enabled`](../mediastreamtrack/enabled) to the inverse of the specified `muting`.

    function setMuting(pc, muting) {
      let senderList = pc.getSenders();

      senderList.forEach(sender) {
        sender.track.enabled = !muting;
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-peerconnection-getsenders">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.getSenders()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`getSenders`

64

79

22

No

51

11

64

64

44

47

11

6.0

See also
--------

-   [WebRTC](https://developer.mozilla.org/en-US/docs/Web/Guide/API/WebRTC_API)
-   [`RTCRtpSender`](../rtcrtpsender)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getSenders" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getSenders</a>
