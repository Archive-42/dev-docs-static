WebRTC API
==========

**WebRTC** (Web Real-Time Communication) is a technology which enables Web applications and sites to capture and optionally stream audio and/or video media, as well as to exchange arbitrary data between browsers without requiring an intermediary. The set of standards that comprise WebRTC makes it possible to share data and perform teleconferencing peer-to-peer, without requiring that the user install plug-ins or any other third-party software.

WebRTC consists of several interrelated APIs and protocols which work together to achieve this. The documentation you'll find here will help you understand the fundamentals of WebRTC, how to set up and use both data and media connections, and more.

Interoperability
----------------

Because implementations of WebRTC are still evolving, and because each browser has [different levels of support for codecs](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/WebRTC_codecs) and WebRTC features, you should *strongly* consider making use of [the Adapter.js library](https://github.com/webrtcHacks/adapter) provided by Google before you begin to write your code.

Adapter.js uses shims and polyfills to smooth over the differences among the WebRTC implementations across the environments supporting it. Adapter.js also handles prefixes and other naming differences to make the entire WebRTC development process easier, with more broadly compatible results. The library is also [available as an NPM package](https://www.npmjs.com/package/webrtc-adapter).

To learn more about Adapter.js, see [Improving compatibility using WebRTC adapter.js](webrtc_api/adapter.js).

WebRTC concepts and usage
-------------------------

WebRTC serves multiple purposes; together with the [Media Capture and Streams API](media_streams_api), they provide powerful multimedia capabilities to the Web, including support for audio and video conferencing, file exchange, screen sharing, identity management, and interfacing with legacy telephone systems including support for sending [DTMF](https://developer.mozilla.org/en-US/docs/Glossary/DTMF) (touch-tone dialing) signals. Connections between peers can be made without requiring any special drivers or plug-ins, and can often be made without any intermediary servers.

Connections between two peers are represented by the [`RTCPeerConnection`](rtcpeerconnection) interface. Once a connection has been established and opened using `RTCPeerConnection`, media streams ([`MediaStream`](mediastream)s) and/or data channels ([`RTCDataChannel`](rtcdatachannel)s) can be added to the connection.

Media streams can consist of any number of tracks of media information; tracks, which are represented by objects based on the [`MediaStreamTrack`](mediastreamtrack) interface, may contain one of a number of types of media data, including audio, video, and text (such as subtitles or even chapter names). Most streams consist of at least one audio track and likely also a video track, and can be used to send and receive both live media or stored media information (such as a streamed movie).

You can also use the connection between two peers to exchange arbitrary binary data using the [`RTCDataChannel`](rtcdatachannel) interface. This can be used for back-channel information, metadata exchange, game status packets, file transfers, or even as a primary channel for data transfer.

***more details and links to relevant guides and tutorials needed***

WebRTC reference
----------------

Because WebRTC provides interfaces that work together to accomplish a variety of tasks, we have divided up the reference by category. Please see the sidebar for an alphabetical list.

### Connection setup and management

These interfaces, dictionaries, and types are used to set up, open, and manage WebRTC connections. Included are interfaces representing peer media connections, data channels, and interfaces used when exchanging information on the capabilities of each peer in order to select the best possible configuration for a two-way media connection.

#### Interfaces

[`RTCPeerConnection`](rtcpeerconnection)  
Represents a WebRTC connection between the local computer and a remote peer. It is used to handle efficient streaming of data between the two peers.

[`RTCDataChannel`](rtcdatachannel)  
Represents a bi-directional data channel between two peers of a connection.

[`RTCDataChannelEvent`](rtcdatachannelevent)  
Represents events that occur while attaching a [`RTCDataChannel`](rtcdatachannel) to a [`RTCPeerConnection`](rtcpeerconnection). The only event sent with this interface is `datachannel`.

[`RTCSessionDescription`](rtcsessiondescription)  
Represents the parameters of a session. Each `RTCSessionDescription` consists of a description [`type`](rtcsessiondescription/type) indicating which part of the offer/answer negotiation process it describes and of the [SDP](https://developer.mozilla.org/en-US/docs/Glossary/SDP) descriptor of the session.

[`RTCStatsReport`](rtcstatsreport)  
Provides information detailing statistics for a connection or for an individual track on the connection; the report can be obtained by calling [`RTCPeerConnection.getStats()`](rtcpeerconnection/getstats). Details about using WebRTC statistics can be found in [WebRTC Statistics API](webrtc_statistics_api).

[`RTCIceCandidate`](rtcicecandidate)  
Represents a candidate Interactive Connectivity Establishment ([ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE)) server for establishing an [`RTCPeerConnection`](rtcpeerconnection).

[`RTCIceTransport`](rtcicetransport)  
Represents information about an [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) transport.

[`RTCPeerConnectionIceEvent`](rtcpeerconnectioniceevent)  
Represents events that occur in relation to ICE candidates with the target, usually an [`RTCPeerConnection`](rtcpeerconnection). Only one event is of this type: `icecandidate`.

[`RTCRtpSender`](rtcrtpsender)  
Manages the encoding and transmission of data for a [`MediaStreamTrack`](mediastreamtrack) on an [`RTCPeerConnection`](rtcpeerconnection).

[`RTCRtpReceiver`](rtcrtpreceiver)  
Manages the reception and decoding of data for a [`MediaStreamTrack`](mediastreamtrack) on an [`RTCPeerConnection`](rtcpeerconnection).

[`RTCTrackEvent`](rtctrackevent)  
The interface used to represent a [`track`](rtcpeerconnection/track_event) event, which indicates that an [`RTCRtpReceiver`](rtcrtpreceiver) object was added to the [`RTCPeerConnection`](rtcpeerconnection) object, indicating that a new incoming [`MediaStreamTrack`](mediastreamtrack) was created and added to the `RTCPeerConnection`.

[`RTCSctpTransport`](rtcsctptransport)  
Provides information which describes a Stream Control Transmission Protocol (**[SCTP](https://developer.mozilla.org/en-US/docs/Glossary/SCTP)**) transport and also provides a way to access the underlying Datagram Transport Layer Security (**[DTLS](https://developer.mozilla.org/en-US/docs/Glossary/DTLS)**) transport over which SCTP packets for all of an [`RTCPeerConnection`](rtcpeerconnection)'s data channels are sent and received.

#### Dictionaries

[`RTCConfiguration`](rtcconfiguration)  
Used to provide configuration options for an [`RTCPeerConnection`](rtcpeerconnection).

[`RTCIceServer`](rtciceserver)  
Defines how to connect to a single [ICE](https://developer.mozilla.org/en-US/docs/Glossary/ICE) server (such as a [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) or [TURN](https://developer.mozilla.org/en-US/docs/Glossary/TURN) server).

[`RTCRtpContributingSource`](rtcrtpcontributingsource)  
Contains information about a given contributing source (CSRC) including the most recent time a packet that the source contributed was played out.

#### Events

[`bufferedamountlow`](rtcdatachannel/bufferedamountlow_event)  
The amount of data currently buffered by the data channel—as indicated by its [`bufferedAmount`](rtcdatachannel/bufferedamount) property—has decreased to be at or below the channel's minimum buffered data size, as specified by [`bufferedAmountLowThreshold`](rtcdatachannel/bufferedamountlowthreshold).

[`close`](rtcdatachannel/close_event)  
The data channel has completed the closing process and is now in the `closed` state. Its underlying data transport is completely closed at this point. You can be notified *before* closing completes by watching for the `closing` event instead.

[`closing`](rtcdatachannel/closing_event)  
The `RTCDataChannel` has transitioned to the `closing` state, indicating that it will be closed soon. You can detect the completion of the closing process by watching for the `close` event.

[`connectionstatechange`](rtcpeerconnection/connectionstatechange_event)  
The connection's state, which can be accessed in [`connectionState`](rtcpeerconnection/connectionstate), has changed.

[`datachannel`](rtcpeerconnection/datachannel_event)  
A new [`RTCDataChannel`](rtcdatachannel) is available following the remote peer opening a new data channel. This event's type is [`RTCDataChannelEvent`](rtcdatachannelevent).

[`error`](rtcdatachannel/error_event)  
An [`RTCErrorEvent`](rtcerrorevent) indicating that an error occurred on the data channel.

[`error`](rtcdtlstransport/error_event)  
An [`RTCErrorEvent`](rtcerrorevent) indicating that an error occurred on the [`RTCDtlsTransport`](rtcdtlstransport). This error will be either `dtls-failure` or `fingerprint-failure`.

[`gatheringstatechange`](rtcicetransport/gatheringstatechange_event)  
The [`RTCIceTransport`](rtcicetransport)'s gathering state has changed.

[`icecandidate`](rtcpeerconnection/icecandidate_event)  
An [`RTCPeerConnectionIceEvent`](rtcpeerconnectioniceevent) which is sent whenever the local device has identified a new ICE candidate which needs to be added to the local peer by calling [`setLocalDescription()`](rtcpeerconnection/setlocaldescription).

[`icecandidateerror`](rtcpeerconnection/icecandidateerror_event)  
An [`RTCPeerConnectionIceErrorEvent`](rtcpeerconnectioniceerrorevent) indicating that an error has occurred while gathering ICE candidates.

[`iceconnectionstatechange`](rtcpeerconnection/iceconnectionstatechange_event)  
Sent to an [`RTCPeerConnection`](rtcpeerconnection) when its ICE connection's state—found in the [`iceconnectionstate`](rtcpeerconnection/iceconnectionstate) property—changes.

[`icegatheringstatechange`](rtcpeerconnection/icegatheringstatechange_event)  
Sent to an [`RTCPeerConnection`](rtcpeerconnection) when its ICE gathering state—found in the [`icegatheringstate`](rtcpeerconnection/icegatheringstate) property—changes.

[`message`](rtcdatachannel/message_event)  
A message has been received on the data channel. The event is of type [`MessageEvent`](messageevent).

[`negotiationneeded`](rtcpeerconnection/negotiationneeded_event)  
Informs the `RTCPeerConnection` that it needs to perform session negotiation by calling [`createOffer()`](rtcpeerconnection/createoffer) followed by [`setLocalDescription()`](rtcpeerconnection/setlocaldescription).

[`open`](rtcdatachannel/open_event)  
The underlying data transport for the `RTCDataChannel` has been successfully opened or re-opened.

[`selectedcandidatepairchange`](rtcicetransport/selectedcandidatepairchange_event)  
The currently-selected pair of ICE candidates has changed for the `RTCIceTransport` on which the event is fired.

[`track`](rtcpeerconnection/track_event)  
The `track` event, of type [`RTCTrackevent`](rtctrackevent) is sent to an [`RTCPeerConnection`](rtcpeerconnection) when a new track is added to the connection following the successful negotiation of the media's streaming.

[`signalingstatechange`](rtcpeerconnection/signalingstatechange_event)  
Sent to the peer connection when its [`signalingstate`](rtcpeerconnection/signalingstate) has changed. This happens as a result of a call to either [`setLocalDescription()`](rtcpeerconnection/setlocaldescription) or [`setRemoteDescription()`](rtcpeerconnection/setremotedescription).

<span class="page-not-created">`statechange`</span>  
The state of the `RTCDtlsTransport` has changed.

[`statechange`](rtcicetransport/statechange_event)  
The state of the `RTCIceTransport` has changed.

<span class="page-not-created">`statechange`</span>  
The state of the `RTCSctpTransport` has changed.

#### Types

[`RTCSctpTransport.state`](rtcsctptransport/state)  
Indicates the state of an [`RTCSctpTransport`](rtcsctptransport) instance.

[`RTCSessionDescriptionCallback`](rtcsessiondescriptioncallback)  
The RTCSessionDescriptionCallback is passed into the [`RTCPeerConnection`](rtcpeerconnection) object when requesting it to create offers or answers.

### Identity and security

These APIs are used to manage user identity and security, in order to authenticate the user for a connection.

<span class="page-not-created">`RTCIdentityProvider`</span>  
Enables a user agent is able to request that an identity assertion be generated or validated.

[`RTCIdentityAssertion`](rtcidentityassertion)  
Represents the identity of the remote peer of the current connection. If no peer has yet been set and verified this interface returns `null`. Once set it can't be changed.

<span class="page-not-created">`RTCIdentityProviderRegistrar`</span>  
Registers an identity provider (idP).

[`RTCIdentityEvent`](rtcidentityevent)  
Represents an identity assertion generated by an identity provider (idP). This is usually for an [`RTCPeerConnection`](rtcpeerconnection). The only event sent with this type is `identityresult`.

[`RTCIdentityErrorEvent`](rtcidentityerrorevent)  
Represents an error associated with the identity provider (idP). This is usually for an [`RTCPeerConnection`](rtcpeerconnection). Two events are sent with this type: `idpassertionerror` and `idpvalidationerror`.

[`RTCCertificate`](rtccertificate)  
Represents a certificate that an [`RTCPeerConnection`](rtcpeerconnection) uses to authenticate.

### Telephony

These interfaces and events are related to interactivity with Public-Switched Telephone Networks (PTSNs). They're primarily used to send tone dialing sounds—or packets representing those tones—across the network to the remote peer.

#### Interfaces

[`RTCDTMFSender`](rtcdtmfsender)  
Manages the encoding and transmission of Dual-Tone Multi-Frequency ([DTMF](https://developer.mozilla.org/en-US/docs/Glossary/DTMF)) signaling for an [`RTCPeerConnection`](rtcpeerconnection).

[`RTCDTMFToneChangeEvent`](rtcdtmftonechangeevent)  
Used by the [`tonechange`](rtcdtmfsender/tonechange_event) event to indicate that a DTMF tone has either begun or ended. This event does not bubble (except where otherwise stated) and is not cancelable (except where otherwise stated).

#### Events

[`tonechange`](rtcdtmfsender/tonechange_event)  
Either a new [DTMF](https://developer.mozilla.org/en-US/docs/Glossary/DTMF) tone has begun to play over the connection, or the last tone in the `RTCDTMFSender`'s [`toneBuffer`](rtcdtmfsender/tonebuffer) has been sent and the buffer is now empty. The event's type is [`RTCDTMFToneChangeEvent`](rtcdtmftonechangeevent).

Guides
------

[Introduction to WebRTC protocols](webrtc_api/protocols)  
This article introduces the protocols on top of which the WebRTC API is built.

[WebRTC connectivity](webrtc_api/connectivity)  
A guide to how WebRTC connections work and how the various protocols and interfaces can be used together to build powerful communication apps.

[Lifetime of a WebRTC session](webrtc_api/session_lifetime)  
WebRTC lets you build peer-to-peer communication of arbitrary data, audio, or video—or any combination thereof—into a browser application. In this article, we'll look at the lifetime of a WebRTC session, from establishing the connection all the way through closing the connection when it's no longer needed.

[Establishing a connection: The perfect negotiation pattern](webrtc_api/perfect_negotiation)  
**Perfect negotiation** is a design pattern which is recommended for your signaling process to follow, which provides transparency in negotiation while allowing both sides to be either the offerer or the answerer, without significant coding needed to differentiate the two.

[Signaling and two-way video calling](webrtc_api/signaling_and_video_calling)  
A tutorial and example which turns a WebSocket-based chat system created for a previous example and adds support for opening video calls among participants. The chat server's WebSocket connection is used for WebRTC signaling.

[Codecs used by WebRTC](https://developer.mozilla.org/en-US/docs/Web/Media/Formats/WebRTC_codecs)  
A guide to the codecs which WebRTC requires browsers to support as well as the optional ones supported by various popular browsers. Included is a guide to help you choose the best codecs for your needs.

[Using WebRTC data channels](webrtc_api/using_data_channels)  
This guide covers how you can use a peer connection and an associated [`RTCDataChannel`](rtcdatachannel) to exchange arbitrary data between two peers.

[Using DTMF with WebRTC](webrtc_api/using_dtmf)  
WebRTC's support for interacting with gateways that link to old-school telephone systems includes support for sending DTMF tones using the [`RTCDTMFSender`](rtcdtmfsender) interface. This guide shows how to do so.

Tutorials
---------

[Improving compatibility using WebRTC adapter.js](webrtc_api/adapter.js)  
The WebRTC organization [provides on GitHub the WebRTC adapter](https://github.com/webrtc/adapter/) to work around compatibility issues in different browsers' WebRTC implementations. The adapter is a JavaScript shim which lets your code to be written to the specification so that it will "just work" in all browsers with WebRTC support.

[Taking still photos with WebRTC](webrtc_api/taking_still_photos)  
This article shows how to use WebRTC to access the camera on a computer or mobile phone with WebRTC support and take a photo with it.

[A simple RTCDataChannel sample](webrtc_api/simple_rtcdatachannel_sample)  
The [`RTCDataChannel`](rtcdatachannel) interface is a feature which lets you open a channel between two peers over which you may send and receive arbitrary data. The API is intentionally similar to the [WebSocket API](websockets_api), so that the same programming model can be used for each.

[Building an internet connected phone with Peer.js](webrtc_api/build_a_phone_with_peerjs)  
This tutorial is a step-by-step guide on how to build a phone using Peer.js

Resources
---------

### Protocols

#### WebRTC-proper protocols

-   [Application Layer Protocol Negotiation for Web Real-Time Communications](https://datatracker.ietf.org/doc/draft-ietf-rtcweb-alpn/)
-   [WebRTC Audio Codec and Processing Requirements](https://datatracker.ietf.org/doc/draft-ietf-rtcweb-audio/)
-   [RTCWeb Data Channels](https://datatracker.ietf.org/doc/draft-ietf-rtcweb-data-channel/)
-   [RTCWeb Data Channel Protocol](https://datatracker.ietf.org/doc/draft-ietf-rtcweb-data-protocol/)
-   [Web Real-Time Communication (WebRTC): Media Transport and Use of RTP](https://datatracker.ietf.org/doc/draft-ietf-rtcweb-rtp-usage/)
-   [WebRTC Security Architecture](https://datatracker.ietf.org/doc/draft-ietf-rtcweb-security-arch/)
-   [Transports for RTCWEB](https://datatracker.ietf.org/doc/draft-ietf-rtcweb-transports/)

#### Related supporting protocols

-   [Interactive Connectivity Establishment (ICE): A Protocol for Network Address Translator (NAT) Traversal for Offer/Answer Protocol](https://datatracker.ietf.org/doc/html/rfc5245)
-   [Session Traversal Utilities for NAT (STUN)](https://datatracker.ietf.org/doc/html/rfc5389)
-   [URI Scheme for the Session Traversal Utilities for NAT (STUN) Protocol](https://datatracker.ietf.org/doc/html/rfc7064)
-   [Traversal Using Relays around NAT (TURN) Uniform Resource Identifiers](https://datatracker.ietf.org/doc/html/rfc7065)
-   [An Offer/Answer Model with Session Description Protocol (SDP)](https://datatracker.ietf.org/doc/html/rfc3264)
-   [Session Traversal Utilities for NAT (STUN) Extension for Third Party Authorization](https://datatracker.ietf.org/doc/draft-ietf-tram-turn-third-party-authz/)

#### WebRTC statistics

-   [WebRTC Statistics API](webrtc_statistics_api)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/">WebRTC 1.0: Real-time Communication Between Browsers</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>The initial definition of the API of WebRTC.</td></tr><tr class="even"><td><a href="https://w3c.github.io/mediacapture-main/">Media Capture and Streams</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>The initial definition of the object conveying the stream of media content.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-fromelement/">Media Capture from DOM Elements</a></td><td><span class="spec-wd">Working Draft</span></td><td>The initial definition on how to obtain stream of content from DOM Elements</td></tr></tbody></table>

In additions to these specifications defining the API needed to use WebRTC, there are several protocols, listed under [resources](#protocols).

See also
--------

-   [`MediaDevices`](mediadevices)
-   [`MediaStreamEvent`](mediastreamevent)
-   [`MediaStreamConstraints`](mediastreamconstraints)
-   [`MediaStreamTrack`](mediastreamtrack)
-   [`MessageEvent`](messageevent)
-   [`MediaStream`](mediastream)
-   [Media Capture and Streams API](media_streams_api)
-   [Firefox multistream and renegotiation for Jitsi Videobridge](https://hacks.mozilla.org/2015/06/firefox-multistream-and-renegotiation-for-jitsi-videobridge/)
-   [Peering Through the WebRTC Fog with SocketPeer](https://hacks.mozilla.org/2015/04/peering-through-the-webrtc-fog-with-socketpeer/)
-   [Inside the Party Bus: Building a Web App with Multiple Live Video Streams + Interactive Graphics](https://hacks.mozilla.org/2014/04/inside-the-party-bus-building-a-web-app-with-multiple-live-video-streams-interactive-graphics/)
-   [Web media technologies](https://developer.mozilla.org/en-US/docs/Web/Media)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API</a>
