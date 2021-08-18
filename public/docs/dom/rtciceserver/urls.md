# RTCIceServers.urls

**Draft**

This page is not complete.

_I'm experimenting with structure for pages documenting members of dictionaries. Please contact [sheppy](https://developer.mozilla.org/en-US/settings) with any feedback._

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [`RTCIceServer`](../rtciceserver) dictionary's `urls` property specifies the URL or URLs of the servers to be used for ICE negotiations. These are typically STUN and/or TURN servers.

## Syntax

    var iceServer = {
                      urls = iceServerUrl | [ url1, ..., urlN ],
                      username: "webrtc", // optional
                      credential: "turnpassword" // optional
                    };

    iceServers.push(iceServer);

The value of this property may be specified as a single URL or as an array of multiple URLs.

## Examples

Let's look a few examples of varying complexity.

### A single ICE server

This example creates a new [`RTCPeerConnection`](../rtcpeerconnection) which will use a [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) server at `stunserver.example.org` to negotiate connections.

    myPeerConnection = new RTCPeerConnection({
      iceServers: [
        {
          urls: "stun:stunserver.example.org"
        }
      ]
    });

Notice that only the `urls` property is provided; the STUN server doesn't require authentication, so this is all that's needed.

### A single ICE server with authentication

The second example creates a new [`RTCPeerConnection`](../rtcpeerconnection) which will use a [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server at `turnserver.example.org` to negotiate connections. Logging into the TURN server will use the username "webrtc" and the creative password "turnpassword".

    myPeerConnection = new RTCPeerConnection({
      iceServers: [
        {
          urls: "turn:turnserver.example.org",
          username: "webrtc",
          credential: "turnpassword"
        }
      ]
    });

### A single ICE server with multiple URLs

The next example creates a new [`RTCPeerConnection`](../rtcpeerconnection) which will use a single [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server which has multiple URLs. This is useful if the server is, for example, available both on "turn" and "turns" schemes, or if there's a fallback address available for the server.

Keep in mind that ICE will try all the URLs you list here, so the more you include, the longer connections will take to establish.

    myPeerConnection = new RTCPeerConnection({
      iceServers: [
        {
          urls: ["turns:turnserver.example.org", "turn:turnserver.example.org"],
          username: "webrtc",
          credential: "turnpassword"
        }
      ]
    });

### Multiple ICE servers

Finally, this example creates a new [`RTCPeerConnection`](../rtcpeerconnection) which will use one of two servers for ICE negotiation. Each server can have one or more URLs, as demonstrated above.

    myPeerConnection = new RTCPeerConnection({
      iceServers: [
        {
          urls: ["turns:turnserver.example.org", "turn:turnserver.example.org"],
          username: "webrtc",
          credential: "turnpassword"
        },
        {
          urls: "stun: stunserver.example.org"
        }
      ]
    });

Two ICE servers are provided. One is a TURN server which can be accessed both over TURN and TURNS. The other is a STUN server. Any number of servers could be listed of any combination of types.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtciceserver-urls">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceServer.urls' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`urls`

Yes

≤79

37

No

?

?

No

Yes

37

?

?

Yes

## See also

- [`RTCIceServer`](../rtciceserver)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceServer/urls" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceServer/urls</a>
