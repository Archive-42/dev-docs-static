RTCPeerConnection.onsignalingstatechange
========================================

The `onsignalingstatechange` event handler property of the **[`RTCPeerConnection`](../rtcpeerconnection)** interface specifies a function to be called when the `signalingstatechange` event occurs on an [`RTCPeerConnection`](../rtcpeerconnection) interface. The function receives as input the event object of type [`Event`](../event); this event is sent when the peer connection's [`signalingState`](signalingstate) changes, which may happen either because of a call to [`setLocalDescription()`](setlocaldescription) or to [`setRemoteDescription()`](setremotedescription).

Syntax
------

    rtcPeerConnection.onsignalingstatechange = errorHandler;

### Value

Set this to a function which you provide that receives an [`Event`](../event) object as input; this contains the `signalingstatechange` event. This event object doesn't provide details about what changed, but you can examine the [`signalingState`](signalingstate) property to determine what the new state is.

You may also, as always, set up a handler for the [`signalingstatechange`](signalingstatechange_event) event using [`addEventListener()`](../eventtarget/addeventlistener):

    myRTCPeerConnection.addEventListener("signalingstatechange", mySignalingStateChangeHandler);

Or, using an anonymous (inline) handler:

    myRTCPeerConnection.addEventListener("signalingstatechange", event => {
      /* handle the event here */
    });

Example
-------

This snippet shows a handler for `signalingstatechange` that looks for the `"have-local-pranswer"` signaling state—indicating that a remote offer has been received and a local description of type `"pranswer"` has been applied in response.

    pc.onsignalingstatechange = function(event) {
      if (pc.signalingState === "have-local-pranswer") {
        // setLocalDescription() has been called with an answer
      }
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-onsignalingstatechange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.onsignalingstatechange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`onsignalingstatechange`

28

15

22

No

43

Promise-based version.

37-43

11

≤37

28

44

43

Promise-based version.

37-43

11

6.0

See also
--------

-   [Signaling and video calling](../webrtc_api/signaling_and_video_calling): A WebRTC example
-   The `signalingstatechange` event and its type, [`Event`](../event).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onsignalingstatechange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onsignalingstatechange</a>
