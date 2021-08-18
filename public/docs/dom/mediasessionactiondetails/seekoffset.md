# MediaSessionActionDetails.seekOffset

The [`MediaSessionActionDetails`](../mediasessionactiondetails) dictionary's `seekOffset` property is an optional value passed into the action handler callback to provide the number of seconds the `seekforward` and `seekbackward` actions should move the playback time by.

## Syntax

    let mediaSessionActionDetails = { seekOffset: deltaTimeInSeconds };

    let deltaTime = mediaSessionActionDetails.seekOffset;

### Value

A floating-point value indicating the time delta in seconds by which to move the playback position relative to its current timestamp. If the offset isn't specified, the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) will choose an appropriate offset automatically. This is typically in the range of five to ten seconds.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#dom-mediasessionactiondetails-seekoffset">Media Session Standard<br />
<span class="small">The definition of 'MediaSessionActionDetails.seekOffset' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`seekOffset`

73

≤79

82

71

?

No

No

No

57

82

Firefox exposes the API, but does not provide a corresponding user-facing media control interface.

No

No

7.0

## See also

- [Media Session API](../media_session_api)
- Refer to the [`MediaSession`](../mediasession) method [`setActionHandler()`](../mediasession/setactionhandler)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSessionActionDetails/seekOffset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSessionActionDetails/seekOffset</a>
