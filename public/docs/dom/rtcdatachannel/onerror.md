# RTCDataChannel.onerror

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `RTCDataChannel.onerror` property is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) which specifies a function to be called when the `error` event is received. When an error occurs on the data channel, the function receives as input an [`ErrorEvent`](../errorevent) object describing the error which occurred.

## Syntax

    RTCDataChannel.onerror = function;

### Value

A function which the browser will call to handle the `error` event when it occurs on the data channel. This function receives as its only input an [`ErrorEvent`](../errorevent) object describing the event which was received. That event object, in turn, describes the error that took place.

## Example

In the example below, a data channel is established, and an `onerror` handler is added to it. The error handler passes information about the error to a UI library's alert box function to present an error message to the user.

    let pc = new RTCPeerConnection();
    let dc = pc.createDataChannel("PlayerControl");

    dc.onerror = function(event) {
      myUILibrary.doAlertBox({
        'Network Error',        // Alert title
        'The error "' + event.message +
               '" occurred while handling player control network messages.',
        event.filename,
        event.lineno,
        event.colno
      });
    }

    /* ... */

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcdatachannel-onerror">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCDataChannel.onerror' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial specification.</td></tr></tbody></table>

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

`onerror`

56

≤79

No

No

43

11

56

56

No

43

11

6.0

## See also

- [WebRTC](../webrtc_api)
- The `error` event and its type, [`ErrorEvent`](../errorevent).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onerror" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCDataChannel/onerror</a>
