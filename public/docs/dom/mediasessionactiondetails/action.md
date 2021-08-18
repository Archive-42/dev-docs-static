# MediaSessionActionDetails.action

The `action` property is the only required property [`MediaSessionActionDetails`](../mediasessionactiondetails) dictionary, specifying the type of media session action which the action handler callback is being executed for.

## Syntax

    let mediaSessionActionDetails = { action: actionType };

    let actionType = mediaSessionActionDetails.action;

### Value

A [`DOMString`](../domstring) specifying which of the action types the callback is being invoked for:

`nexttrack`  
Advances playback to the next track.

`pause`  
Pauses playback of the media.

`play`  
Begins (or resumes) playback of the media.

`previoustrack`  
Moves back to the previous track.

`seekbackward`  
Seeks backward through the media from the current position. The [`MediaSessionActionDetails`](../mediasessionactiondetails) property [`seekOffset`](seekoffset) specifies the amount of time to seek backward.

`seekforward`  
Seeks forward from the current position through the media. The [`MediaSessionActionDetails`](../mediasessionactiondetails) property [`seekOffset`](seekoffset) specifies the amount of time to seek forward.

`seekto`  
Moves the playback position to the specified time within the media. The time to which to seek is specified in the [`MediaSessionActionDetails`](../mediasessionactiondetails) property [`seekTime`](seektime). If you intend to perform multiple `seekto` operations in rapid succession, you can also specify the [`MediaSessionActionDetails`](../mediasessionactiondetails) property [`fastSeek`](fastseek) property with a value of `true`. This lets the browser know it can take steps to optimize repeated operations, and is likely to result in improved performance.

`skipad`  
Skips past the currently playing advertisement or commercial. This action may or may not be available, depending on the platform and [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent), or may be disabled due to subscription level or other circumstances.

`stop`  
Halts playback entirely.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#dom-mediasessionactiondetails-action">Media Session Standard<br />
<span class="small">The definition of 'MediaSessionActionDetails.action' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

BCD tables only load in the browser

- Media Session API
- Refer to the [`MediaSession`](../mediasession) method [`setActionHandler()`](../mediasession/setactionhandler)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSessionActionDetails/action" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSessionActionDetails/action</a>
