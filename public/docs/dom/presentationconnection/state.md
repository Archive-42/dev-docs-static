# PresentationConnection.state

The `state` attribute reflects the [presentation connection](https://www.w3.org/TR/presentation-api/#dfn-presentation-connection)'s current state. Depending on the current [`PresentationConnectionState`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnectionstate), the `state` attribute can hold one of the following values.

- **`connecting`**: The user agent is attempting to [establish a presentation connection](https://www.w3.org/TR/presentation-api/#dfn-establish-a-presentation-connection) with the [destination browsing context](https://www.w3.org/TR/presentation-api/#dfn-destination-browsing-context). This is the initial state when a [`PresentationConnection`](https://www.w3.org/TR/presentation-api/#idl-def-presentationconnection) object is created.
- **`connected`**: The [presentation connection](https://www.w3.org/TR/presentation-api/#dfn-presentation-connection) is established and communication is possible.
- **`closed`**: The [presentation connection](https://www.w3.org/TR/presentation-api/#dfn-presentation-connection) has been closed or could not be opened. The connection may be reopened by calling `reconnect()`. No communication is possible in this state.
- **`terminated`**: The [receiving browsing context](https://www.w3.org/TR/presentation-api/#dfn-receiving-browsing-context) has terminated. Any [presentation connection](https://www.w3.org/TR/presentation-api/#dfn-presentation-connection) to that [presentation](https://www.w3.org/TR/presentation-api/#dfn-presentation) has also terminated and cannot be reopened. No communication is possible.

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

`state`

48

≤79

51-88

No

Yes

No

No

48

51-79

Yes

No

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PresentationConnection/state" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PresentationConnection/state</a>
