RTCConfiguration.iceServers
===========================

### Value

BCD tables only load in the browser

The [`RTCConfiguration`](../rtcconfiguration) dictionary's `iceServers` property is an array of [`RTCIceServer`](../rtciceserver) objects, each of which describes a single [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) or [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server to use for negotiation purposes.

    let rtcConfiguration = {
      iceServers: [ iceServer1... ]
    };

    let rtcConfiguration.iceServers = [ iceServer1... ];

An array of zero or more [`RTCIceServer`](../rtciceserver) objects, each of which describes one [STUN or TURN server](../webrtc_api/protocols) for the ICE agent to use [during the connection's negotiation](../webrtc_api/session_lifetime#establishing_the_connection). Each object must at least have an [`urls`](../rtciceserver/urls) property, which is an array of one or more strings, each providing one server's URL.

If the array is empty, or if the `iceServers` option isn't specified, the ICE agent will negotiate without the use of any servers, which will limit the connection to local peers.

How the list of servers you provide is used is up to the implementation of the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent). While it can be useful to provide a second server as a fallback in case the first is offline, listing too many servers can delay the user's connection being established, depending on the network's performance and how many servers get used for negotiation before a connection is established.

If the list of servers is changed while a connection is already active by calling the [`RTCPeerConnection`](../rtcpeerconnection) method [`setConfiguration()`](../rtcpeerconnection/setconfiguration), no immediate effect occurs. However, the new list of servers is used for any future renegotiation, such as while handling an [ICE restart](../webrtc_api/session_lifetime#ice_restart).

The configuration below opens a new peer connection, specifying two servers for the ICE agent to use for negotiation. The first one, `stun:stun.services.mozilla.com`, requires authentication, so the username and password are provided. The second server has two URLs: `stun:stun.example.com` and `stun:stun-1.example.com`.

    var configuration = { iceServers: [{
                              urls: "stun:stun.services.mozilla.com",
                              username: "louis@mozilla.com",
                              credential: "webrtcdemo"
                          }, {
                              urls: ["stun:stun.example.com", "stun:stun-1.example.com"]
                          }]
    };

    var pc = new RTCPeerConnection(configuration);

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcconfiguration-iceservers">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCConfiguration.iceServers' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

-   [Introduction to WebRTC protocols](../webrtc_api/protocols)
-   [Lifetime of a WebRTC connection](../webrtc_api/session_lifetime#establishing_the_connection)
-   [Establishing a connection: The WebRTC perfect negotiation pattern](../webrtc_api/perfect_negotiation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCConfiguration/iceServers" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCConfiguration/iceServers</a>
