RTCIceServer.credentialType
===========================

The [`RTCIceServer`](../rtciceserver) dictionary's `credentialType` property is a string value from the [`RTCIceCredentialType` enum](#rtcicecredentialtype_enum) which indicates what type of credential the [`RTCIceServer.credential`](credential) value is. The default is `password`.

Syntax
------

    var iceServer = {
                      ...
                      credentialType = newCredentialType,
                      ...
                    };

    var credentialType = iceServer.credentialType;

    iceServer.credentialType = newCredentialType;

### Value

The permitted values are found in the [`RTCIceCredentialType`](../rtcicecredentialtype) enumerated string type:

`oauth`  
The [`RTCIceServer`](../rtciceserver) requires the use of OAuth 2.0 to authenticate in order to use the ICE server described. This process is detailed in [RFC 7635](https://tools.ietf.org/html/rfc7635). This property was formerly called `token`.

`password`  
The `RTCIceServer` requires a username and password to authenticate prior to using the described ICE server.

Example
-------

This example creates a new [`RTCPeerConnection`](../rtcpeerconnection) which will use a [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server at `turnserver.example.org` to negotiate connections. Logging into the TURN server will use the username "webrtc" and the creative password "turnpassword".

    myPeerConnection = new RTCPeerConnection({
      iceServers: [
        {
          urls: "turn:turnserver.example.org",  // A TURN server
          username: "webrtc",
          credential: "turnpassword",
          credentialType: "password"
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

`credentialType`

Yes

≤79

47

No

?

?

No

Yes

47

?

?

Yes

See also
--------

-   [`RTCIceServer`](../rtciceserver)
-   [`RTCIceServer.credential`](credential)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceServer/credentialType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceServer/credentialType</a>
