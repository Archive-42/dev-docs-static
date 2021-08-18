RTCPeerConnection.onicecandidateerror
=====================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCPeerConnection.onicecandidateerror` property is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) which specifies a function which is called to handle the `icecandidateerror` event when it occurs on an [`RTCPeerConnection`](../rtcpeerconnection) instance. This event is fired when an error occurs during the [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) candidate gathering process.

Syntax
------

    RTCPeerConnection.onicecandidateerror = eventHandler;

### Value

This should be set to a function you provide which is passed a single parameter: an [`RTCPeerConnectionIceErrorEvent`](../rtcpeerconnectioniceerrorevent) object describing the `icecandidateerror` event. The event offers properties describing the error to help you handle it appropriately.

Example
-------

    pc.onicecandidateerror = function(event) {
      if (event.errorCode >= 300 && event.errorCode <= 699) {
        // STUN errors are in the range 300-699. See RFC 5389, section 15.6
        // for a list of codes. TURN adds a few more error codes; see
        // RFC 5766, section 15 for details.
      } else if (event.errorCode >= 700 && event.errorCode <= 799) {
        // Server could not be reached; a specific error number is
        // provided but these are not yet specified.
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcpeerconnection-onicecandidateerror">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCPeerConnection.onicecandidateerror' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`onicecandidateerror`

No

No

?

No

?

14.1

No

No

?

?

14.5

No

See also
--------

-   The `icecandidateerror` event and its type, [`RTCPeerConnectionIceErrorEvent`](../rtcpeerconnectioniceerrorevent).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onicecandidateerror" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/onicecandidateerror</a>
