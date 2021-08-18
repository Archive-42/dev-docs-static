# RTCDataChannel: closing event

The `closing` event is sent to an [`RTCDataChannel`](../rtcdatachannel) just before the channel begins the process of shutting down its underlying data transport.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onclosing"><code>RTCDataChannel.onclosing</code></a></td></tr></tbody></table>

## Description

While the `closing` event is sent to the channel just before beginning to close the channel's data transport, the [`close`](close_event) event is sent once the closing process is complete.

## Examples

This example updates a connection status interface when the `closing` event arrives.

First, an example using [`addEventListener()`](../eventtarget/addeventlistener):

    dataChannel.addEventListener("closing", ev => {
      myConnectionStatus.icon = closingIcon;
      myConnectionStatus.text = "Connection closing";
    });

You can also set the [`onclosing`](onclosing) event handler property directly:

    pc.onclosing = ev => {
     myConnectionStatus.icon = closingIcon;
     myConnectionStatus.text = "Connection closing";
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dfn-closing">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel: closing event' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.RTCDataChannel.closing_event`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [WebRTC API](../webrtc_api)
- [Signaling and video calling](../webrtc_api/signaling_and_video_calling)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/closing_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/closing_event</a>
