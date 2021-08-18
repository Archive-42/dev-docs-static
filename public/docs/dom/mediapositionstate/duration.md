MediaPositionState.duration
===========================

The [`MediaPositionState`](../mediapositionstate) dictionary's `duration` property is used when calling the [`MediaSession`](../mediasession) method [`setPositionState()`](../mediasession/setpositionstate) to provide the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) with the overall total duration in seconds of the media currently being performed. This information can then, in turn, be used by the user agent to provide a user interface which displays media playback information to the viewer.

For example, a browser might use this information along with the [`position`](position) property and the [`navigator.mediaSession.playbackState`](../mediasession/playbackstate), as well as the session's [`metadata`](../mediasession/metadata) to provide an integrated common user interface showing the currently playing media as well as standard pause, play, forward, reverse, and other controls.

Syntax
------

    let positionState = { duration: durationInSeconds };

    let durationInSeconds = positionState.duration;

### Value

A floating-point value indicating the overall duration, in seconds, of the media being performed. This value should always be positive. To indicate media of unknown or indeterminate length, such as an ongoing live stream, specify a value of positive infinity (`Infinity`).

Example
-------

In this example, an app performing a live stream provides information to the browser by preparing a [`MediaPositionState`](../mediapositionstate) object and submitting it by calling [`navigator.mediaSession.setPositionState()`](../mediasession/setpositionstate).

    let positionState = {
      duration: Infinity;
      playbackRate: 1.0;
      position: 0.0;
    };

    navigator.mediaSession.setPositionState(positionState);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#dom-mediapositionstate-duration">Media Session Standard<br />
<span class="small">The definition of 'MediaPositionState.duration' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.MediaPositionState.duration`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaPositionState/duration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaPositionState/duration</a>
