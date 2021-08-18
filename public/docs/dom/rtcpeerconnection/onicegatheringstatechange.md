RTCPeerConnection.onicegatheringstatechange
===========================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCPeerConnection.onicegatheringstatechange` property is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) which specifies a function to be called when the `icegatheringstatechange` event is sent to an [`RTCPeerConnection`](../rtcpeerconnection) instance. This happens when the ICE gathering state—that is, whether or not the ICE agent is actively gathering candidates—changes.

You don't need to watch for this event unless you have specific reasons to want to closely monitor the state of ICE gathering.

Syntax
------

    RTCPeerConnection.onicegatheringstatechange = eventHandler;

### Value

A function you provide which is passed a single parameter: an [`Event`](../event) object containing the `icegatheringstatechange` event. You can determine the new state of ICE gathering by looking at the value of the [`RTCPeerConnection.iceGatheringState`](icegatheringstate) property.

Example
-------

This example updates status information presented to the user to let them know what's happening by examining the current value of the [`iceGatheringState`](icegatheringstate) property each time it changes and changing the contents of a status display based on the new information.

The status is presented as text in a [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) element:

    <div id="iceStatus"></div>

The actual event handler looks like this:

    pc.onicegatheringstatechange = function() {
      let label = "Unknown";

      switch(pc.iceGatheringState) {
        case "new":
        case "complete":
          label = "Idle";
          break;
        case "gathering":
          label = "Determining route";
          break;
      }

      document.getElementById("iceStatus").innerHTML = label;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-onicegatheringstatechange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.onicegatheringstatechange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`onicegatheringstatechange`

59

15

22

No

43

Promise-based version.

37-43

11

59

59

44

43

Promise-based version.

37-43

11

7.0

See also
--------

-   The `icegatheringstatechange` event and its type, [`Event`](../event).
-   [`RTCPeerConnection.iceGatheringState`](icegatheringstate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onicegatheringstatechange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onicegatheringstatechange</a>
