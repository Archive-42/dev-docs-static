# MediaSessionActionDetails.fastSeek

The Boolean property `fastSeek` in the [`MediaSessionActionDetails`](../mediasessionactiondetails) dictionary is an optional value which, when specified and `true`, indicates that the requested `seekto` operation is part of an ongoing series of `seekto` operations. Your handler should take steps to return as quickly as possible by skipping any steps of its operation which are only necessary when the seek operation is complete.

Once `fastSeek` is `false` or not present, the repeating series of `seekto` actions is complete and you can finalize the state of your web app or content.

## Syntax

    let mediaSessionActionDetails = { fastSeek: shouldFastSeek };

    let shouldFastSeek = mediaSessionActionDetails.fastSeek;

### Value

A Boolean which is `true` if the action is part of an ongoing series of seek actions which should be treated as part of an overall seek operation. If the value is `false` or this property isn't present, the seek is final.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#dom-mediasessionactiondetails-fastseek">Media Session Standard<br />
<span class="small">The definition of 'MediaSessionActionDetails.fastSeek' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`fastSeek`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSessionActionDetails/fastSeek" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSessionActionDetails/fastSeek</a>
