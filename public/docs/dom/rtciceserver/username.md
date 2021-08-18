# RTCIceServer.username

**Draft**

This page is not complete.

_I'm experimenting with structure for pages documenting members of dictionaries. Please contact [sheppy](https://developer.mozilla.org/en-US/settings) with any feedback._

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`RTCIceServer`](../rtciceserver) dictionary's `username` property is a string which specifies the username to use when authenticating with the [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) server being described.

This value is used when the `RTCIceServer` describes a [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server.

## Syntax

    var iceServer = {
                      ...
                      username = username,
                      ...
                    };

    var username = iceServer.username;

    iceServer.username = newUsername;

## Example

This example creates a new [`RTCPeerConnection`](../rtcpeerconnection) which will use a [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server at `turnserver.example.org` to negotiate connections. Logging into the TURN server will use the username "webrtc" and the creative password "turnpassword".

    myPeerConnection = new RTCPeerConnection({
      iceServers: [
        {
          urls: "turn:turnserver.example.org",  // A TURN server
          username: "webrtc",
          credential: "turnpassword"
        }
      ]
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtciceserver-username">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceServer.username' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

## Browser compatibility

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

`username`

Yes

≤79

23

No

?

?

No

Yes

24

?

?

Yes

## See also

- [`RTCIceServer`](../rtciceserver)
- [`RTCIceServer.credential`](credential)
- [`RTCIceServer.credentialType`](credentialtype)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceServer/username" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceServer/username</a>
