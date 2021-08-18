RTCIceCandidate.usernameFragment
================================

The read-only `usernameFragment` property on the [`RTCIceCandidate`](../rtcicecandidate) interface is a string indicating the username fragment ("ufrag") that uniquely identifies a single ICE interaction session.

This value is specified when creating the [`RTCIceCandidate`](../rtcicecandidate) by setting the corresponding [`usernameFragment`](../rtcicecandidateinit/usernamefragment) value in the [`RTCIceCandidateInit`](../rtcicecandidateinit) object when creating a new candidate with [`new RTCIceCandidate()`](rtcicecandidate). Note that 24 bits of the username fragment are required to be randomized by the browser. See [Randomization](#randomization) below for details.

If you instead call `RTCIceCandidate()` with a string parameter containing the `candidate` m-line text, the value of `usernameFragment` is extracted from the m-line.

Syntax
------

    var ufrag = RTCIceCandidate.usernameFragment;

### Value

A [`DOMString`](../domstring) containing the username fragment (usually referred to in shorthand as "ufrag" or "ice-ufrag") that, along with the ICE password ("ice-pwd"), uniquely identifies a single ongoing ICE interaction, including for any communication with the [STUN](https://developer.mozilla.org/en-US/docs/Glossary/STUN) server. The string may be up to 256 characters long, and has no default value.

#### Randomization

At least 24 bits of the text in the `ufrag` are required to be randomly selected by the ICE layer at the beginning of the ICE session. The specifics for which bits are random and what the remainder of the `ufrag` text are left up to the browser implementation to decide. For example, a browser might choose to always use a 24-character `ufrag` in which bit 4 of each character is randomly selected between 0 and 1. Another example: it might take a user-defined string and append three 8-bit random bytes to the end. Or perhaps every character is entirely random.

Usage notes
-----------

ICE uses the `usernameFragment` and password to ensure message integrity. This avoids crosstalk among multiple ongoing ICE sessions, but, more importantly, helps secure ICE transactions (and all of WebRTC by extension) against attacks that might try to inject themselves into an ICE exchange.

**Note:** There is no API to obtain the ICE password, for what should be fairly obvious security reasons.

The `usernameFragment` and password both change every time an [ICE restart](../webrtc_api/session_lifetime#ice_restart) occurs.

Example
-------

Although the WebRTC infrastructure will filter out obsolete candidates for you after an ICE restart, you can do it yourself if you're trying to absolutely minimize the number of messages going back and forth.

To do so, you can compare the value of `usernameFragment` to the current `usernameFragment` being used for the connection after receiving the candidate from the signaling server and before caling [`addIceCandidate()`](../rtcpeerconnection/addicecandidate) to add it to the set of possible candidates.

When the web app receives a message from the signaling server that includes a candidate to be added to the [`RTCPeerConnection`](../rtcpeerconnection), you can (and generally *should*) call `addIceCandidate()`. There's not typically a need to manually worry about filtering the candidates.

However, let's imagine that we do need to minimize traffic. The function below, `ssNewCandidate()`, is called when a message, `signalMsg`, arrives from the signaling server that contains an ICE candidate to be added to the `RTCPeerConnection`. To avoid including candidates obsoleted by an ICE restart, we can use code like this:

    const ssNewCandidate = signalMsg => {
      let candidate = new RTCIceCandidate(signalMsg.candidate);
      let receivers = pc.getReceivers();

      receivers.forEach(receiver => {
        let parameters = receiver.transport.getParameters();

        if (parameters.usernameFragment === candidate.usernameFragment) {
          return;
        }
      });

      pc.addIceCandidate(candidate)
        .catch(reportError);
    }

This walks through the list of the [`RTCRtpReceiver`](../rtcrtpreceiver) objects being used to receive ICE data, and looks to see if the `usernameFragment` indicated in the candidate matches any of them. If it does, `ssNewCandidate()` aborts. Otherwise, after checking every receiver, it adds the new candidate to the connection.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/webrtc-pc/#dom-rtcicecandidate-usernamefragment">WebRTC 1.0: Real-time Communication Between Browsers<br />
<span class="small">The definition of 'RTCIceCandidate.usernameFragment' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`usernameFragment`

74

79

67

No

62

14.1

74

74

67

53

14.5

11.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/usernameFragment" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/RTCIceCandidate/usernameFragment</a>
