RTCDtlsTransport
================

Properties
----------

The `RTCDtlsTransport` interface provides access to information about the Datagram Transport Layer Security (**[DTLS](https://developer.mozilla.org/en-US/docs/Glossary/DTLS)**) transport over which a [`RTCPeerConnection`](rtcpeerconnection)'s [RTP](https://developer.mozilla.org/en-US/docs/Glossary/RTP) and [RTCP](https://developer.mozilla.org/en-US/docs/Glossary/RTCP) packets are sent and received by its [`RTCRtpSender`](rtcrtpsender) and [`RTCRtpReceiver`](rtcrtpreceiver) objects.

A DTLS transport is also used to provide information about [SCTP](https://developer.mozilla.org/en-US/docs/Glossary/SCTP) packets transmitted and received by an connection's [data channels](rtcdatachannel).

Features of the DTLS transport include the addition of security to the underlying transport; the `RTCDtlsTransport` interface can be used to obtain information about the underlying transport and the security added to it by the DTLS layer.

 [`iceTransport`](rtcdtlstransport/icetransport) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> undefined  
The read-only `RTCDtlsTransport` property `iceTransport` contains a reference to the underlying `RTCIceTransport`.

 [`state`](rtcdtlstransport/state) undefined  
`WebRTC`

Description
-----------

### Allocation of DTLS transports

`RTCDtlsTransport` objects are created when an app calls either [`setLocalDescription()`](rtcpeerconnection/setlocaldescription) or [`setRemoteDescription()`](rtcpeerconnection/setremotedescription). The number of DTLS transports created and how they're used depends on the bundling mode used when creating the [`RTCPeerConnection`](rtcpeerconnection).

Whether bundling is used depends on what the other endpoint is able to negotiate. All browsers support bundling, so when both endpoints are browsers, you can rest assured that bundling will be used.

Some non-browser legacy endpoints, however, may not support bundle. To be able to negotiate with such endpoints (or to exclude them entirely), the [`RTCConfiguration`](rtcconfiguration) property [`bundlePolicy`](rtcconfiguration/bundlepolicy) may be provided when creating the connection. The `bundlePolicy` [lets you control](rtcpeerconnection#rtcbundlepolicy_enum) how to negotiate with these legacy endpoints. The default policy is `"balanced"`, which provides a balance between performance and compatibility.

For example, to create the connection using the highest level of bundling:

    const rtcConfig = {
      bundlePolicy: "max-bundle"
    };

    const pc = new RTCPeerConnection(rtcConfig);

[Bundling](https://webrtcstandards.info/sdp-bundle/) lets you use one `RTCDtlsTransport` to carry the data for multiple higher-level transports, such as multiple [`RTCRtpTransceiver`](rtcrtptransceiver)s.

#### When not using BUNDLE

When the connection is created without using BUNDLE, each RTP or RTCP component of each [`RTCRtpTransceiver`](rtcrtptransceiver) has its own `RTCDtlsTransport`; that is, every [`RTCRtpSender`](rtcrtpsender) and [`RTCRtpReceiver`](rtcrtpreceiver), has its own transport, and all [`RTCDataChannel`](rtcdatachannel) objects share a transport dedicated to SCTP.

#### When using BUNDLE

When the connection is using BUNDLE, each `RTCDtlsTransport` object represents a group of [`RTCRtpTransceiver`](rtcrtptransceiver) objects. If the connection was created using `max-compat` mode, each transport is responsible for handling all of the communications for a given type of media (audio, video, or data channel). Thus, a connection that has any number of audio and video channels will always have exactly one DTLS transport for audio and one for video communications.

Because transports are established early in the negotiation process, it's likely that it won't be known until after they're created whether or not the remote peer supports bundling or not. For this reason, you'll sometimes see separate transports created at first, one for each track, then see them get bundled up once it's known that bundling is possible. If your code accesses [`RTCRtpSender`](rtcrtpsender)s and/or [`RTCRtpReceiver`](rtcrtpreceiver)s directly, you may encounter situations where they're initially separate, then half or more of them get closed and the senders and receivers updated to refer to the appropriate remaining `RTCDtlsTransport` objects.

### Data channels

[`RTCDataChannel`](rtcdatachannel)s use [SCTP](https://developer.mozilla.org/en-US/docs/Glossary/SCTP) to communicate. All of a peer connection's data channels share a single [`RTCSctpTransport`](rtcsctptransport), found in the connection's [`sctp`](rtcpeerconnection/sctp) property.

You can, in turn, identify the `RTCDtlsTransport` used to securely encapsulate the data channels' SCTP communications by looking at the `RTCSctpTransport` object's <span class="page-not-created">`transport`</span> property.

Examples
--------

This example presents a function, `tallySenders()`, which iterates over an `RTCPeerConnection`'s [`RTCRtpSender`](rtcrtpsender)s, tallying up how many of them are in various states. The function returns an object containing properties whose values indicate how many of the senders are in each state.

    let pc = new RTCPeerConnection({ bundlePolicy: "max-bundle" });

    /* ... */

    function tallySenders(pc) {
      let results = {
        transportMissing: 0,
        connectionPending: 0,
        connected: 0,
        closed: 0,
        failed: 0,
        unknown: 0
      };

      let senderList = pc.getSenders();
      senderList.forEach(sender => {
        let transport = sender.transport;

        if (!transport) {
          results.transportMissing++;
        } else {
          switch(transport.state) {
            case "new":
            case "connecting":
              results.connectionPending++;
              break;
           case "connected":
              results.connected++;
              break;
           case "closed":
              results.closed++;
              break;
           case "failed":
              results.failed++;
              break;
           default:
              results.unknown++;
              break;
          }
        }
      });
      return results;
    }

Note that in this code, the `new` and `connecting` states are being treated as a single `connectionPending` status in the returned object.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdtlstransport">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDtlsTransport' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RTCDtlsTransport`

72

12

No

See [bug 1307996](https://bugzil.la/1307996).

No

60

No

72

72

No

See [bug 1307996](https://bugzil.la/1307996).

50

No

11.0

`getRemoteCertificates`

72

12

No

See [bug 1307996](https://bugzil.la/1307996).

No

60

No

72

72

No

See [bug 1307996](https://bugzil.la/1307996).

50

No

11.0

`iceTransport`

72

15

No

See [bug 1307996](https://bugzil.la/1307996).

No

60

No

72

72

No

See [bug 1307996](https://bugzil.la/1307996).

50

No

11.0

`onerror`

72

12

No

See [bug 1307996](https://bugzil.la/1307996).

No

60

No

72

72

No

See [bug 1307996](https://bugzil.la/1307996).

50

No

11.0

`onstatechange`

72

12

No

See [bug 1307996](https://bugzil.la/1307996).

No

60

No

72

72

No

See [bug 1307996](https://bugzil.la/1307996).

50

No

11.0

`state`

72

12

No

See [bug 1307996](https://bugzil.la/1307996).

No

60

No

72

72

No

See [bug 1307996](https://bugzil.la/1307996).

50

No

11.0

`statechange_event`

72

12

No

See [bug 1307996](https://bugzil.la/1307996).

No

60

No

72

72

No

See [bug 1307996](https://bugzil.la/1307996).

50

No

11.0

See also
--------

-   [`RTCRtpSender.transport`](rtcrtpsender/transport) and [`RTCRtpReceiver.transport`](rtcrtpreceiver/transport)
-   <span class="page-not-created">`RTCSctpTransport.transport`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDtlsTransport</a>
