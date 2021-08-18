RTCPeerConnection.getTransceivers()
===================================

The [`RTCPeerConnection`](../rtcpeerconnection) interface's `getTransceivers()` method returns a list of the [`RTCRtpTransceiver`](../rtcrtptransceiver) objects being used to send and receive data on the connection.

Syntax
------

    transceiverList = rtcPeerConnection.getTransceivers();

### Parameters

None.

### Return value

An array of the [`RTCRtpTransceiver`](../rtcrtptransceiver) objects representing the transceivers handling sending and receiving all media on the `RTCPeerConnection`. The list is in the order in which the transceivers were added to the connection.

Example
-------

The following snippet of code stops all transceivers associated with an `RTCPeerConnection`.

    pc.getTransceivers().forEach(transceiver => {
      transceiver.stop();
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-gettransceivers">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.getTransceivers()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`getTransceivers`

69

79

59

No

56

11

79

69

59

48

11

10.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [Signaling and video calling](../webrtc_api/signaling_and_video_calling)
-   [`RTCPeerConnection.addTransceiver()`](addtransceiver)
-   [`Array.forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getTransceivers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getTransceivers</a>
