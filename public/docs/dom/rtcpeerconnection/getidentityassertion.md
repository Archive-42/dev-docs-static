RTCPeerConnection.getIdentityAssertion()
========================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCPeerConnection.getIdentityAssertion()` method initiates the gathering of an identity assertion. This has an effect only if the [`signalingState`](signalingstate) is not `"closed"`.

The method returns immediately. If the assertion cannot be generated, an `idpassertionerror` will be sent to the object.

It is not expected for the application dealing with the `RTCPeerConnection`: this is automatically done; an explicit call only allows to anticipate the need.

Syntax
------

    pc.getIdentityAssertion();

*There is neither parameter nor return value for this method.*

Example
-------

    var pc = new PeerConnection();

    pc.getIdentityAssertion(); // Not mandatory, but we know that we will need it in the future.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-identity/#dfn-getidentityassertion">Identity for WebRTC<br />
<span class="small">The definition of 'RTCPeerConnection.getIdentityAssertion()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`getIdentityAssertion`

No

≤18-79

22

No

43

Promise-based version.

37-43

No

No

No

44

43

Promise-based version.

37-43

No

6.0

See also
--------

-   [WebRTC](../webrtc_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getIdentityAssertion" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/getIdentityAssertion</a>
