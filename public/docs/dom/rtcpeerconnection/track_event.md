RTCPeerConnection: track event
==============================

The `track` event is sent to the [`ontrack`](ontrack) event handler on [`RTCPeerConnection`](../rtcpeerconnection)s after a new track has been added to an [`RTCRtpReceiver`](../rtcrtpreceiver) which is part of the connection.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../rtctrackevent"><code>RTCTrackEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="ontrack"><code>ontrack</code></a></td></tr></tbody></table>

By the time this event is delivered, the new track has been fully added to the peer connection. See [Track event types](../rtctrackevent#track_event_types) in [RTCTrackEvent](../rtctrackevent) for details.

Examples
--------

This example shows code that creates a new [`RTCPeerConnection`](../rtcpeerconnection), then adds a new `track` event handler.

    pc = new RTCPeerConnection({
      iceServers: [
        {
          urls: "turn:fake.turnserver.url",
          username: "someusername",
          credential: "somepassword"
        }
      ]
    });

    pc.addEventListener("track", e => {
      videoElement.srcObject = e.streams[0];
      hangupButton.disabled = false;
    }, false);

The event handler assigns the new track's first stream to an existing [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, identified using the variable `videoElement`.

You can also assign the event handler function to the [`ontrack`](ontrack) property, rather than use [`addEventListener()`](../eventtarget/addeventlistener).

    pc.ontrack = e => {
      videoElement.srcObject = e.streams[0];
      hangupButton.disabled = false;
      return false;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#event-track">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'track' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`track_event`

64

≤18

22

No

43

11

64

64

44

43

?

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/track_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/track_event</a>
