# MediaSession.setPositionState()

The [`MediaSession`](../mediasession) method `setPositionState()` is used to update the current document's media playback position and speed for presentation by user's device in any kind of interface that provides details about ongoing media. This can be particularly useful if your code implements a player for type of media not directly supported by the browser.

Call this method on the `navigator` object's [`mediaSession`](../navigator/mediasession) object.

## Syntax

    navigator.mediaSession.setPositionState(stateDict);

### Parameters

`stateDict` <span class="badge inline optional">Optional</span>  
An object conforming to the [`MediaPositionState`](../mediapositionstate) dictionary, providing updated information about the playback position and speed of the document's ongoing media. If the object is empty, the existing playback state information is cleared.

### Return value

[`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

### Exceptions

`TypeError`  
This error can occur in an array of circumstances:

- The specified [`MediaPositionState`](../mediapositionstate) object's [`duration`](../mediapositionstate/duration) is missing, negative, or `null`.
- [`position`](../mediapositionstate/position) is missing or null, or is either negative or greater than `duration`.
- The [`playbackRate`](../mediapositionstate/playbackrate) is zero.

## Example

Below is a function which updates the position state of the current [`MediaSession`](../mediasession) track.

    function updatePositionState() {
      navigator.mediaSession.setPositionState({
        duration: audioEl.duration,
        playbackRate: audioEl.playbackRate,
        position: audioEl.currentTime
      });
    }

We can use this function when updating [`media session metadata`](../mediametadata) and within callbacks for actions, such as below.

    navigator.mediaSession.setActionHandler('seekbackward', details => {

      // our time to skip
      const skipTime = details.seekOffset || 10;

      // set our position
      audioEl.currentTime = Math.max(audioEl.currentTime - skipTime, 0);
      updatePositionState();

    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#dom-mediasession-setpositionstate">Media Session Standard<br />
<span class="small">The definition of 'MediaSession.setPositionState()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`setPositionState`

73

≤79

82

71

No

Yes

No

No

57

82

Firefox exposes the API, but does not provide a corresponding user-facing media control interface.

No

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSession/setPositionState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSession/setPositionState</a>
