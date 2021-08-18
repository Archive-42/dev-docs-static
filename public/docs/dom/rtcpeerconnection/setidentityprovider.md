RTCPeerConnection.setIdentityProvider()
=======================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCPeerConnection.setIdentityProvider()` method sets the Identity Provider (IdP) to the triplet given in parameter: its name, the protocol used to communicate with it (optional) and an optional username. The IdP will be used only when an assertion is needed.

If the [`signalingState`](signalingstate) is set to `"closed"`, an `InvalidStateError` is raised.

Syntax
------

    pc.setIdentityProvider(domainname [, protocol] [, username]);

*There is no return value for this method.*

### Parameters

*domainname*  
Is a [`DOMString`](../domstring) is the domain name where the IdP is.

 *protocol* <span class="badge inline optional">Optional</span>   
Is a [`DOMString`](../domstring) representing the protocol used to communicate with the IdP. It defaults to `"default"` and is used to determine the URL where the IdP is listening.

 *username* <span class="badge inline optional">Optional</span>   
Is a [`DOMString`](../domstring) representing the username associated with the IdP.

Example
-------

    var pc = new PeerConnection();

    pc.setIdentityAssertion("developer.mozilla.org");

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-identity/#dfn-setidentityprovider">Identity for WebRTC<br />
<span class="small">The definition of 'RTCPeerConnection.setIdentityProvider()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`setIdentityProvider`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setIdentityProvider" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCPeerConnection/setIdentityProvider</a>
