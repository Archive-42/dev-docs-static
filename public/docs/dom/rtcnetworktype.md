RTCNetworkType
==============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [WebRTC](webrtc_api) `RTCNetworkType` enumerated type defines a set of strings used to identify the type of network used by a connection between two peers. This type is used as the value or the following properties:

-   [`RTCIceCandidate`](rtcicecandidate)'s [`networkType`](rtcicecandidatestats/networktype)
-   <span class="page-not-created">`RTCStunServerConnectionStats`</span>'s <span class="page-not-created">`networkType`</span>

Values
------

`bluetooth`  
A Bluetooth connection is used by the described connection.

`cellular`  
The connection uses a cellular data service to connect. This includes all cellular data services including EDGE (2G), HSPA (3G), LTE (4G), and NR (5G).

`ethernet`  
The described connection uses an Ethernet network.

`wifi`  
The described connection uses WiFi.

`wimax`  
The described connection uses a [WiMAX](https://en.wikipedia.org/wiki/WiMAX) network.

`vpn`  
The connection uses a Virtual Private Network (VPN). The VPN obscures the underlying network type, which is not discernible.

`unknown`  
The user's browser is unable or unwilling to identify the underlying connection technology used by the described connection. This may be because the browser isn't able to determine the network type for some reason or it may be intentionally getting obscured for security reasons, such as to avoid [device fingerprinting](https://en.wikipedia.org/wiki/Device_fingerprinting).

**Note:** Keep in mind that the specified value only reflects the initial connection between the local peer and the next hop along the network toward reaching the remote peer. For example, if the `networkType` is `wifi` but the user is connected using a cellular hotspot, the connection will be bottlenecked by the underlying cellular network (and any other networks between the two peers).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#rtcnetworktype-enum">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCNetworkType' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCNetworkType`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCNetworkType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCNetworkType</a>
