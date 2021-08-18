# MediaSessionActionDetails

The [Media Session API'](media_session_api)s `MediaSessionActionDetails` dictionary is the type used by the sole input parameter into the callback which is executed when a [media session action](#media_action_types) occurs. It specifies the type of action which needs to be performed as well as the data needed to perform the action.

## Properties

[`action`](mediasessionactiondetails/action)  
A [Media Session action type](mediasessionaction) string taken from the `MediaSessionAction` enumerated type, indicating which type of action needs to be performed. See [Media action types](#media_action_types) below for possible values.

[`fastSeek`](mediasessionactiondetails/fastseek) <span class="badge inline optional">Optional</span>  
An `seekto` action may _optionally_ include this property, which is a Boolean value indicating whether or not to perform a "fast" seek. A "fast" seek is a seek being performed in a rapid sequence, such as when fast-forwarding or reversing through the media, rapidly skipping through it. This property can be used to indicate that you should use the shortest possible method to seek the media. `fastSeek` is not included on the final action in the seek sequence in this situation.

[`seekOffset`](mediasessionactiondetails/seekoffset) <span class="badge inline optional">Optional</span>  
If the `action` is either `seekforward` or `seekbackward` and this property is present, it is a floating point value which indicates the number of seconds to move the play position forward or backward. If this property isn't present, those actions should choose a reasonable default distance to skip forward or backward (such as 7 or 10 seconds).

[`seekTime`](mediasessionactiondetails/seektime) <span class="badge inline optional">Optional</span>  
If the `action` is `seekto`, this property must be present and must be a floating-point value indicating the absolute time within the media to move the playback position to, where 0 indicates the beginning of the media. This property is not present for other action types.

## Media action types

A media session action's type is specified using a string from the `MediaSessionAction` enumerated type.

### Values

Each of the actions is a common media session control request. Implement support for each of these in order to allow that type of action to be performed. The following strings identify the currently available types of media session action:

`nexttrack`  
Advances playback to the next track.

`pause`  
Pauses playback of the media.

`play`  
Begins (or resumes) playback of the media.

`previoustrack`  
Moves back to the previous track.

`seekbackward`  
Seeks backward through the media from the current position. The [`MediaSessionActionDetails`](mediasessionactiondetails) property [`seekOffset`](mediasessionactiondetails/seekoffset) specifies the amount of time to seek backward.

`seekforward`  
Seeks forward from the current position through the media. The [`MediaSessionActionDetails`](mediasessionactiondetails) property [`seekOffset`](mediasessionactiondetails/seekoffset) specifies the amount of time to seek forward.

`seekto`  
Moves the playback position to the specified time within the media. The time to which to seek is specified in the [`MediaSessionActionDetails`](mediasessionactiondetails) property [`seekTime`](mediasessionactiondetails/seektime). If you intend to perform multiple `seekto` operations in rapid succession, you can also specify the [`MediaSessionActionDetails`](mediasessionactiondetails) property [`fastSeek`](mediasessionactiondetails/fastseek) property with a value of `true`. This lets the browser know it can take steps to optimize repeated operations, and is likely to result in improved performance.

`skipad`  
Skips past the currently playing advertisement or commercial. This action may or may not be available, depending on the platform and [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent), or may be disabled due to subscription level or other circumstances.

`stop`  
Halts playback entirely.

## Examples

### Adding action handlers

This example implements seek forward and backward actions for an audio player by setting up the `seekforward` and `seekbackward` action handlers.

    let skipTime = 10; // Time to skip in seconds

    navigator.mediaSession.setActionHandler('seekforward', details => {
     // User clicked "Seek Forward" media notification icon.
     audio.currentTime = Math.min(audio.currentTime + skipTime,
                   audio.duration);
    });

    navigator.mediaSession.setActionHandler('seekbackward', details => {
     // User clicked "Seek Backward" media notification icon.
     audio.currentTime = Math.max(audio.currentTime - skipTime, 0);
    });

In this case, both the `seekforward` and `seekbackward` handlers are using a fixed distance, ignoring the time specified by the [`MediaSessionActionDetails`](mediasessionactiondetails) passed into the handler.

### Supporting multiple actions in one handler function

You can also, if you prefer, use a single function to handle multiple action types, by checking the value of the `MediaSessionActionDetails` object's [`action`](mediasessionactiondetails/action) property:

    let skipTime = 7;

    navigator.mediaSession.setActionHandler("seekforward", handleSeek);
    navigator.mediaSession.setActionHandler("seekbackward", handleSeek);

    function handleSeek(details) {
      switch(details.action) {
        case "seekforward":
          audio.currentTime = Math.min(audio.currentTime + skipTime,
                  audio.duration);
          break;
        case "seekbackward":
          audio.currentTime = Math.max(audio.currentTime - skipTime, 0);
          break;
      }
    }

Here, the `handleSeek()` function handles both `seekbackward` and `seekforward` actions.

### Using data provided by MediaSessionActionDetails

In this example, instead of seeking a specified distance, the `seekforward` and `seekbackward` handlers use the time specified in the `MediaSessionActionDetails` object's [`seekOffset`](mediasessionactiondetails/seekoffset) property.

    navigator.mediaSession.setActionHandler("seekforward", handleSeek);
    navigator.mediaSession.setActionHandler("seekbackward", handleSeek);

    function handleSeek(details) {
      switch(details.action) {
        case "seekforward":
          audio.currentTime = Math.min(audio.currentTime + details.seekOffset,
                                       audio.duration);
          break;
        case "seekbackward":
          audio.currentTime = Math.max(audio.currentTime - details.seekOffset, 0);
          break;
      }
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#dictdef-mediasessionactiondetails">Media Session Standard<br />
<span class="small">The definition of 'MediaSessionActionDetails' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`MediaSessionActionDetails`

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

`action`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSessionActionDetails" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSessionActionDetails</a>
