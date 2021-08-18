# MediaSessionActionDetails.seekTime

The [`MediaSessionActionDetails`](../mediasessionactiondetails) dictionary's `seekTime` property is always included when a `seekto` action is sent to the action handler callback. Its value is the absolute time, in seconds, to move the current play position to.

To change the time by an offset rather than moving to an absolute time, the `seekforward` or `seekbackward` actions should be used instead.

## Syntax

    let mediaSessionActionDetails = { seekTime: absTimeInSeconds };

    let absTime = mediaSessionActionDetails.seekTime;

### Value

A floating-point value indicating the absolute time in seconds into the media to which to move the current play position.

## Usage notes

To perform a "fast" seek (such as when issuing multiple `seekto` actions in sequence while handling a scrubbing operation, the details object's [`fastSeek`](fastseek) property's value is set to `true`, indicating that you should minimize or eliminate anything you do while handling the action that is only necessary at the final step.

If the value of `fastSeek` is false, or `fastSeek` is missing, the action should be treated as the final action of the operation, and you should finalize any details that need to be handled.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#dom-mediasessionactiondetails-seektime">Media Session Standard<br />
<span class="small">The definition of 'MediaSessionActionDetails.seekTime' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`seekTime`

73

≤79

No

?

No

No

No

57

No

No

No

7.0

## See also

- [Media Session API](../media_session_api)
- Refer to the [`MediaSession`](../mediasession) method [`setActionHandler()`](../mediasession/setactionhandler)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSessionActionDetails/seekTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSessionActionDetails/seekTime</a>
