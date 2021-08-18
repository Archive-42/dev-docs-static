RTCIceServer.credential
=======================

**Draft**

This page is not complete.

*I'm experimenting with structure for pages documenting members of dictionaries. Please contact [sheppy](https://developer.mozilla.org/en-US/settings) with any feedback.*

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`RTCIceServer`](../rtciceserver) dictionary's `credential` property is a string providing the credential to use when connecting to the described server. This is typically a password, key, or other secret.

This value is used when the `RTCIceServer` describes a [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server.

Syntax
------

    var iceServer = {
                      ...
                      credential = credential,
                      ...
                    };

    var credential = iceServer.credential;

    iceServer.credential = newCredential;

Example
-------

This example creates a new [`RTCPeerConnection`](../rtcpeerconnection) which uses a [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server at `turnserver.example.org` to negotiate connections. Logging into the TURN server uses the username "webrtc" and the creative password "turnpassword".

    myPeerConnection = new RTCPeerConnection({
      iceServers: [
        {
          urls: "turn:turnserver.example.org",  // A TURN server
          username: "webrtc",
          credential: "turnpassword"
        }
      ]
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtciceserver-credential">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceServer.credential' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`credential`

Yes

≤79

22

No

?

?

No

Yes

24

?

?

Yes

See also
--------

-   [`RTCIceServer`](../rtciceserver)
-   [`RTCIceServer.credentialType`](credentialtype)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceServer/credential" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceServer/credential</a>
