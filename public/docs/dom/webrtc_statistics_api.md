WebRTC Statistics API
=====================

**Draft**

This page is not complete.

The WebRTC API has a vast array of statistics available, covering the entire breadth of the WebRTC connectivity system, from sender to receiver and peer to peer.

Collecting statistics
---------------------

You can collect statistics at various levels throughout the WebRTC hierarchy of objects. Most broadly, you can call [`getStats()`](rtcpeerconnection/getstats) on an [`RTCPeerConnection`](rtcpeerconnection) to get statistics for the connection overall. In this example, a new [`RTCPeerConnection`](rtcpeerconnection) is created, and then [`setInterval()`](windoworworkerglobalscope/setinterval) is used to set the function `getConnectionStats()` to be called every second.

That function, in turn, uses [`getStats()`](rtcpeerconnection/getstats) to obtain statistics for the connection and to make use of that data.

    try {
      myPeerConnection = new RTCPeerConnection(pcOptions);

      statsInterval = window.setInterval(getConnectionStats, 1000);
      /* add event handlers, etc */
    } catch(err) {
      console.error("Error creating RTCPeerConnection: " + err);
    }

    function getConnectionStats() {
      myPeerConnection.getStats(null).then(stats => {
        var statsOutput = "";

        stats.forEach(report => {
          if (report.type === "inbound-rtp" && report.kind === "video") {
            Object.keys(report).forEach(statName => {
              statsOutput += `<strong>${statName}:</strong> ${report[statName]}<br>\n`;
            });
          }
        });

        document.querySelector(".stats-box").innerHTML = statsOutput;
      });
    }

When the promise returned by `getStats()` is fulfilled, the resolution handler receives as input an [`RTCStatsReport`](rtcstatsreport) object containing the statistics information. This object contains a [`Map`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map) of named dictionaries based on [`RTCStats`](rtcstats) and its affiliated types.

This example specifically looks for the report whose [`type`](rtcstats/type) is `inbound-rtp` and whose [`kind`](rtcrtpstreamstats/kind) is `video`. This way, we look only at the video-related statistics for the local [`RTCRtpReceiver`](rtcrtpreceiver) responsible for receiving the streamed media.

Commonly used statistics
------------------------

Reference
---------

The [`RTCStatsReport`](rtcstatsreport) object contains a map of named objects based one of the [`RTCStats`](rtcstats) dictionary's subclasses. Upon looking up a statistic category by name, you get an object containing the corresponding data. The table below shows the statistic categories and the corresponding dictionaries; for each statistic category, the full hierarchy of `RTCStats`-based dictionaries are listed, so you can easily find all the available values.

<table><caption>Mapping of statistic category names to the dictionaries they implement</caption><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Statistic category name (<a href="rtcstatstype"><code>RTCStatsType</code></a>)</th><th>Description</th><th>Dictionaries implemented</th></tr></thead><tbody><tr class="odd"><td><code>candidate-pair</code></td><td>Statistics describing the change from one <a href="rtcicetransport"><code>RTCIceTransport</code></a> to another, such as during an <a href="webrtc_api/session_lifetime#ice_restart">ICE restart</a>.</td><td><ul><li><a href="rtcicecandidatepairstats"><code>RTCIceCandidatePairStats</code></a><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="even"><td><code>certificate</code></td><td>Statistics about a certificate being used by an <a href="rtcicetransport"><code>RTCIceTransport</code></a>.</td><td><ul><li><span class="page-not-created"><code>RTCCertificateStats</code></span><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="odd"><td><code>codec</code></td><td>Statistics about a specific codec being used by streams being sent or received by this connection.</td><td><span class="page-not-created"><code>RTCCodecStats</code></span><br />
<a href="rtcstats"><code>RTCStats</code></a></td></tr><tr class="even"><td><code>csrc</code></td><td>Statistics for a single contributing source (CSRC) that contributed to one of the connection's inbound RTP streams.</td><td><ul><li><span class="page-not-created"><code>RTCRtpContributingSourceStats</code></span><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="odd"><td><code>data-channel</code></td><td>Statistics related to one <a href="rtcdatachannel"><code>RTCDataChannel</code></a> on the connection.</td><td><ul><li><span class="page-not-created"><code>RTCDataChannelStats</code></span><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="even"><td><code>ice-server</code></td><td>Statistics about the connection to an <a href="https://developer.mozilla.org/en-US/docs/Glossary/ICE">ICE</a> server (<a href="https://developer.mozilla.org/en-US/docs/Glossary/STUN">STUN</a> or <a href="https://developer.mozilla.org/en-US/docs/Glossary/TURN">TURN</a>.</td><td><ul><li><span class="page-not-created"><code>RTCIceServerStats</code></span><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="odd"><td><code>inbound-rtp</code></td><td>Statistics describing the state of one of the connection's inbound data streams.</td><td><ul><li><a href="rtcinboundrtpstreamstats"><code>RTCInboundRtpStreamStats</code></a><ul><li><span class="page-not-created"><code>RTCReceivedRtpStreamStats</code></span><ul><li><a href="rtcrtpstreamstats"><code>RTCRtpStreamStats</code></a><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></li></ul></li></ul></td></tr><tr class="even"><td><code>local-candidate</code></td><td>Statistics about a local ICE candidate associated with the connection's <a href="rtcicetransport"><code>RTCIceTransport</code></a>s.</td><td><ul><li><a href="rtcicecandidatestats"><code>RTCIceCandidateStats</code></a><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="odd"><td><code>media-source</code></td><td>Statistics about the media produced by the <a href="mediastreamtrack"><code>MediaStreamTrack</code></a> attached to an RTP sender. The dictionary this key maps to depends on the track's <a href="mediastreamtrack/kind"><code>kind</code></a>.</td><td><ul><li><span class="page-not-created"><code>RTCAudioSourceStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCVideoSourceStats</code></span><ul><li><span class="page-not-created"><code>RTCMediaSourceStats</code></span><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></li></ul><span class="page-not-created"><code>RTCAudioSourceStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCVideoSourceStats</code></span></td></tr><tr class="even"><td><code>outbound-rtp</code></td><td>Statistics describing the state of one of the outbound data streams on this connection.</td><td><ul><li><a href="rtcoutboundrtpstreamstats"><code>RTCOutboundRtpStreamStats</code></a><ul><li><span class="page-not-created"><code>RTCSentRtpStreamStats</code></span><ul><li><a href="rtcrtpstreamstats"><code>RTCRtpStreamStats</code></a><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></li></ul></li></ul></td></tr><tr class="odd"><td><code>peer-connection</code></td><td>Statistics describing the state of the <a href="rtcpeerconnection"><code>RTCPeerConnection</code></a>.</td><td><ul><li><span class="page-not-created"><code>RTCPeerConnectionStats</code></span><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="even"><td><code>receiver</code></td><td>Statistics related to a specific <a href="rtcrtpreceiver"><code>RTCRtpReceiver</code></a> and the media associated with that receiver. The specific type of object representing the statistics depends on the media <code>kind</code>.</td><td><ul><li><span class="page-not-created"><code>RTCAudioReceiverStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCVideoReceiverStats</code></span><ul><li><span class="page-not-created"><code>RTCAudioHandlerStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCVideoHandlerStats</code></span><ul><li><span class="page-not-created"><code>RTCMediaHandlerStats</code></span><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></li></ul></li></ul></td></tr><tr class="odd"><td><code>remote-candidate</code></td><td>Statistics about a remote ICE candidate associated with the connection's <a href="rtcicetransport"><code>RTCIceTransport</code></a>s.</td><td><ul><li><a href="rtcicecandidatestats"><code>RTCIceCandidateStats</code></a><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="even"><td><code>remote-inbound-rtp</code></td><td>Statistics describing the state of the inbound data stream from the perspective of the remote peer.</td><td><ul><li><span class="page-not-created"><code>RTCRemoteInboundRtpStreamStats</code></span><ul><li><span class="page-not-created"><code>RTCReceivedRtpStreamStats</code></span><ul><li><a href="rtcrtpstreamstats"><code>RTCRtpStreamStats</code></a><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></li></ul></li></ul></td></tr><tr class="odd"><td><code>remote-outbound-rtp</code></td><td>Statistics describing the state of the outbound data stream from the perpsective of the remote peer.</td><td><ul><li><a href="rtcremoteoutboundrtpstreamstats"><code>RTCRemoteOutboundRtpStreamStats</code></a><ul><li><span class="page-not-created"><code>RTCSentRtpStreamStats</code></span><ul><li><a href="rtcrtpstreamstats"><code>RTCRtpStreamStats</code></a><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></li></ul></li></ul></td></tr><tr class="even"><td><code>sctp-transport</code></td><td>Statistics about an <a href="rtcsctptransport"><code>RTCSctpTransport</code></a>.</td><td><ul><li><span class="page-not-created"><code>RTCSctpTransportStats</code></span><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="odd"><td><code>sender</code></td><td>Statistics related to a specific <a href="rtcrtpsender"><code>RTCRtpSender</code></a> and the media associated with that sender. The type of object representing this statistic depends on the <code>kind</code> of the media.</td><td><ul><li><span class="page-not-created"><code>RTCAudioSenderStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCVideoSenderStats</code></span><ul><li><span class="page-not-created"><code>RTCAudioHandlerStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCVideoHandlerStats</code></span><ul><li><span class="page-not-created"><code>RTCMediaHandlerStats</code></span><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></li></ul></li></ul></td></tr><tr class="even"><td><code>stream</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>Statistics about a particular media <a href="mediastream"><code>MediaStream</code></a>. This has been obsoleted since the transition to WebRTC being track-based rather than stream-based.</td><td><ul><li><span class="page-not-created"><code>RTCMediaStreamStats</code></span><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="odd"><td><code>track</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><p>Statistics related to a specific <a href="mediastreamtrack"><code>MediaStreamTrack</code></a>'s attachment to one of the connection's senders or receivers. The referenced object's type depends on the track type.</p><div class="notecard note"><p>These statistics have all been moved to <code>media-source</code>, <code>sender</code>, <code>receiver</code>, <code>outbound-rtp</code>, and <code>inbound-rtp</code>, and this statistic category type is thus obsolete and shouldn't be used anymore.</p></div></td><td><ul><li><span class="page-not-created"><code>RTCSenderVideoTrackAttachmentStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCSenderAudioTrackAttachmentStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCReceiverVideoTrackAttachmentStats</code></span> <em>or</em> <span class="page-not-created"><code>RTCReceiverAudioTrackAttachmentStats</code></span><ul><li><span class="page-not-created"><code>RTCMediaHandlerStats</code></span><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></li></ul></td></tr><tr class="even"><td><code>transceiver</code></td><td>Statistics related to a specific <a href="rtcrtptransceiver"><code>RTCRtpTransceiver</code></a>.</td><td><ul><li><span class="page-not-created"><code>RTCRtpTransceiverStats</code></span><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></td></tr><tr class="odd"><td><code>transport</code></td><td>Statistics about a transport used by the connection.</td><td><ul><li><span class="page-not-created"><code>RTCTransportStats</code></span><ul><li><a href="rtcstats"><code>RTCStats</code></a></li></ul></li></ul></td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-stats/#dom-rtcstatstype">Identifiers for WebRTC's Statistics API<br />
<span class="small">The definition of 'WebRTC statistics types' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Compatibility for individual statistic types</td></tr><tr class="even"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcstatsreport">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCStatsReport' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Compatibility of statistic reporting</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.RTCStatsType`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_Statistics_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_Statistics_API</a>