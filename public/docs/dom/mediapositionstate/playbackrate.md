MediaPositionState.playbackRate
===============================

The [`MediaPositionState`](../mediapositionstate) dictionary's `playbackRate` property is used when calling the [`MediaSession`](../mediasession) method [`setPositionState()`](../mediasession/setpositionstate) to tell the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) the rate at which media is currently being played. This information can then, in turn, be used by the user agent to provide a user interface which displays media playback information to the viewer.

For example, a browser might use this information along with the [`position`](position) property and the [`navigator.mediaSession.playbackState`](../mediasession/playbackstate), as well as the session's [`metadata`](../mediasession/metadata) to provide an integrated common user interface showing the currently playing media as well as standard pause, play, forward, reverse, and other controls.

Syntax
------

    let positionState = { playbackRate: rate };

    let playbackRate = positionState.playbackRate;

### Value

A floating-point value specifying a multiplier corresponding to the current relative rate at which the media being performed is playing. A value of 1.0 indicates the media is playing forward at normal speed, while higher values indicate that the media is being played faster than normal. Lower values indicate the media is being played more slowly. Negative values can be specified to indicate the media is playing in reverse, with decreasing values then indicating faster and faster reverse playback.

**Note:** A value of 0.0 is not permitted.

Example
-------

In this example, an app is updating the browser to let it know that the user has clicked a button causing the playback to shift to a double-speed mode. It begins by creating a [`MediaPositionState`](../mediapositionstate) object, then submits it to the browser it by calling [`navigator.mediaSession.setPositionState()`](../mediasession/setpositionstate).

    let positionState = {
      duration: myMediaDuration;
      playbackRate: 2.0;
      position: myMediaPosition;
    };

    navigator.mediaSession.setPositionState(positionState);

Note the value 2.0 as the `playbackRate`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#dom-mediapositionstate-playbackrate">Media Session Standard<br />
<span class="small">The definition of 'MediaPositionState.playbackRate' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.MediaPositionState.playbackRate`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaPositionState/playbackRate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaPositionState/playbackRate</a>
