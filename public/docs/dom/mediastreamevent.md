# MediaStreamEvent

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `MediaStreamEvent` interface represents events that occurs in relation to a [`MediaStream`](mediastream). Two events of this type can be thrown: `addstream` and `removestream`.

## Properties

_A [`MediaStreamEvent`](mediastreamevent) being an [`Event`](event), this event also implements these properties_.

[`MediaStreamEvent.stream`](mediastreamevent/stream) <span class="badge inline readonly">Read only </span>  
Contains the [`MediaStream`](mediastream) containing the stream associated with the event.

## Constructors

[`MediaStreamEvent()`](mediastreamevent/mediastreamevent)  
Returns a new `MediaStreamEvent`. It takes two parameters, the first being a [`DOMString`](domstring) representing the type of the event; the second a dictionary containing the [`MediaStream`](mediastream) it refers to.

## Methods

A [`MediaStreamEvent`](mediastreamevent) being an [`Event`](event), this event also implements these properties. There is no specific [`MediaStreamEvent`](mediastreamevent) method.

## Examples

    pc.onaddstream = function( ev ) {
      alert("A stream (id: '" + ev.stream.id + "') has been added to this connection.");
    };

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

`MediaStreamEvent`

Yes

15

Yes

No

Yes

?

Yes

Yes

?

Yes

?

Yes

`MediaStreamEvent`

Yes

15

Yes

No

Yes

?

Yes

Yes

?

Yes

?

Yes

`stream`

Yes

15

Yes

No

Yes

?

Yes

Yes

?

?

?

Yes

## See also

- [WebRTC](webrtc_api)
- Its usual target: [`RTCPeerConnection`](rtcpeerconnection).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaStreamEvent</a>
