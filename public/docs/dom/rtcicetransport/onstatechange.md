# RTCIceTransport.onstatechange

The `onstatechange` event handler for the [`RTCIceTransport`](../rtcicetransport) interface is a property which specifies a function to serve as the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for the `statechange` event that is fired whenever the transport's [`state`](state) changes.

## Syntax

    RTCIceTransport.onstatechange = stateChangeHandler;

### Value

Set this property to reference a function you provide that is called by the WebRTC layer when the [`RTCIceTransport`](../rtcicetransport) object's [`state`](state) changes.

The event handler receives as its sole input an [`Event`](../event) object describing the `statechange` event which occurred. To determine the new state, examine the value of [`state`](state).

## Example

This snippet establishes a handler for the `statechange` event that looks to see if the transport has entered the `"failed"` state, which indicates that the connection has failed with no chance of being automatically restored.

    var iceTransport = pc.getSenders()[0].transport.iceTransport;

    iceTransport.onstatechange = function(event) {
      if (iceTransport.state == "failed") {
        handleFailure(pc);
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicetransport-onstatechange">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceTransport.onstatechange' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`onstatechange`

75

79

No

No

62

No

75

75

No

54

No

11.0

## See also

- The `statechange` event and its type, [`Event`](../event).
- The other event handlers for `RTCIceTransport`: [`ongatheringstatechange`](ongatheringstatechange) and [`onselectedcandidatepairchange`](onselectedcandidatepairchange)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/onstatechange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceTransport/onstatechange</a>
