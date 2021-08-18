RTCPeerConnection: icecandidate event
=====================================

An `icecandidate` event is sent to an [`RTCPeerConnection`](../rtcpeerconnection) when an [`RTCIceCandidate`](../rtcicecandidate) has been identified and added to the local peer by a call to [`RTCPeerConnection.setLocalDescription()`](setlocaldescription). The event handler should transmit the candidate to the remote peer over the signaling channel so the remote peer can add it to its set of remote candidates.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../rtcpeerconnectioniceevent"><code>RTCPeerConnectionIceEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onicecandidate"><code>RTCPeerConnection.onicecandidate</code></a></td></tr></tbody></table>

Description
-----------

There are three reasons why the `icecandidate` event is fired on an [`RTCPeerConnection`](../rtcpeerconnection).

### Sharing a new candidate

The majority of `icecandidate` events are fired to indicate that a new candidate has been gathered. This candidate needs to be delivered to the remote peer over the signaling channel your code manages.

    rtcPeerConnection.onicecandidate = (event) => {
      if (event.candidate) {
        sendCandidateToRemotePeer(event.candidate)
      } else {
        /* there are no more candidates coming during this negotiation */
      }
    }

The remote peer, upon receiving the candidate, will add the candidate to its candidate pool by calling [`addIceCandidate()`](addicecandidate), passing in the [`candidate`](../rtcpeerconnectioniceevent/candidate) string you have passed along using the signaling server.

### Indicating the end of a generation of candidates

When an ICE negotiation session runs out of candidates to propose for a given [`RTCIceTransport`](../rtcicetransport), it has completed gathering for a **generation** of candidates. That this has occurred is indicated by an `icecandidate` event whose [`candidate`](../rtcpeerconnectioniceevent/candidate) string is empty (`""`).

You should deliver this to the remote peer just like any standard candidate, as described under [Sharing a new candidate](#sharing_a_new_candidate) above. This ensures that the remote peer is given the end-of-candidates notification as well. As you see in the code in the previous section, every candidate is sent to the other peer, including any that might have an empty candidate string. Only candidates for which the event's [`candidate`](../rtcpeerconnectioniceevent/candidate) property is `null` are not forwarded across the signaling connection.

The end-of-candidates indication is described in [section 9.3 of the Trickle ICE draft specification](https://datatracker.ietf.org/doc/html/draft-ietf-mmusic-trickle-ice-02#section-9.3) (note that the section number is subject to change as the specification goes through repeated drafts).

### Indicating that ICE gathering is complete

Once all ICE transports have finished gathering candidates and the value of the [`RTCPeerConnection`](../rtcpeerconnection) object's [`iceGatheringState`](icegatheringstate) has made the transition to `complete`, an `icecandidate` event is sent with the value of `complete` set to `null`.

This signal exists for backward compatibility purposes and does *not* need to be delivered onward to the remote peer (which is why the code snippet above checks to see if `event.candidate` is `null` prior to sending the candidate along.

If you need to perform any special actions when there are no further candidates expected, you're much better off watching the ICE gathering state by watching for [`icegatheringstatechange`](icegatheringstatechange_event) events:

    pc.addEventListener("icegatheringstatechange", ev => {
      switch(pc.iceGatheringState) {
        case "new":
          /* gathering is either just starting or has been reset */
          break;
        case "gathering":
          /* gathering has begun or is ongoing */
          break;
        case "complete":
          /* gathering has ended */
          break;
      }
    });

As you can see in this example, the `icegatheringstatechange` event lets you know when the value of the [`RTCPeerConnection`](../rtcpeerconnection) property [`iceGatheringState`](icegatheringstate) has been updated. If that value is now `complete`, you know that ICE gathering has just ended.

This is a more reliable approach than looking at the individual ICE messages for one indicating that the ICE session is finished.

Examples
--------

This example creates a simple handler for the `icecandidate` event that uses a function called `sendMessage()` to create and send a reply to the remote peer through the signaling server.

First, an example using [`addEventListener()`](../eventtarget/addeventlistener):

    pc.addEventListener("icecandidate", ev => {
      if (ev.candidate) {
        sendMessage({
          type: "new-ice-candidate",
          candidate: event.candidate
        });
      }
    }, false);

You can also set the [`onicecandidate`](onicecandidate) event handler property directly:

    pc.onicecandidate = ev => {
      if (ev.candidate) {
        sendMessage({
          type: "new-ice-candidate",
          candidate: event.candidate
        });
      }
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-icecandidate">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'icecandidate' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`icecandidate_event`

24

15

22

No

43

11

Yes

25

44

43

?

6.0

See also
--------

-   [WebRTC API](../webrtc_api)
-   [Signaling and video calling](../webrtc_api/signaling_and_video_calling)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icecandidate_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/icecandidate_event</a>
