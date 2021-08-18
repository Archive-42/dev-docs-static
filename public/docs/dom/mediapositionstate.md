# MediaPositionState

The Media Session API's `MediaPositionState` dictionary is used to represent the current playback position of a media session. Its contents can be used by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) to provide a user interface displaying information about the playback position and duration of the media currently being performed.

## Properties

[`duration`](mediapositionstate/duration)  
A floating-point value giving the total duration of the current media in seconds. This should always be a positive number, with positive infinity (`Infinity`) indicating media without a defined end, such as a live stream.

[`playbackRate`](mediapositionstate/playbackrate)  
A floating-point value indicating the rate at which the media is being played, as a ratio relative to its normal playback speed. Thus, a value of 1 is playing at normal speed, 2 is playing at double speed, and so forth. Negative values indicate that the media is playing in reverse; -1 indicates playback at the normal speed but backward, -2 is double speed in reverse, and so on.

[`position`](mediapositionstate/position)  
A floating-point value indicating the last reported playback position of the media in seconds. This must always be a positive value.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#dictdef-mediapositionstate">Media Session Standard<br />
<span class="small">The definition of 'MediaPositionState' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.MediaPositionState`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaPositionState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaPositionState</a>
