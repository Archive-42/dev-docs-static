MediaPositionState.position
===========================

The [`MediaPositionState`](../mediapositionstate) dictionary's `position` property is used when calling the [`MediaSession`](../mediasession) method [`setPositionState()`](../mediasession/setpositionstate) to provide the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) with the current playback position, in seconds, of the currently-playing media. This information is then, in turn, used by the user agent to provide a user interface which displays media playback information to the viewer.

For example, a browser might use this information along with the [`position`](position) property and the [`navigator.mediaSession.playbackState`](../mediasession/playbackstate), as well as the session's [`metadata`](../mediasession/metadata) to provide an integrated common user interface showing the currently playing media as well as standard pause, play, forward, reverse, and other controls.

Syntax
------

    let positionState = { position: timeInSeconds };

    let duration = positionState.duration;

### Value

A floating-point value indicating the current playback position within the media currently being performed, in seconds. This value should always be zero or more.

Example
-------

In this example, a player for a non-standard media file format, written in JavaScript, uses [`setInterval()`](../windoworworkerglobalscope/setinterval) to establish a callback which fires once per second to refresh the position information by calling [`setPositionState()`](../mediasession/setpositionstate). If the media is still playing when the interval is fired, `setPositionState()` is called with an object that specifies the duration, playback rate, and position as reported by a `myMedia` object that describes the track being played.

If the media is not playing, [`clearInterval()`](../windoworworkerglobalscope/clearinterval) is used to remove the interval handler.

    let positionInterval = window.setInterval(() => {
      if (myMedia.isPlaying) {
        navigator.mediaSession.setPositionState({
          duration: myMedia.trackDurationInSeconds,
          playbackRate: myMedia.playbackRate,
          position: myMedia.trackPlayPositionInSeconds
        });
      } else {
        window.clearInterval(positionInterval);
      }
    }, 1000);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#dom-mediapositionstate-position">Media Session Standard<br />
<span class="small">The definition of 'MediaPositionState.position' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `api.MediaPositionState.position`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaPositionState/position" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaPositionState/position</a>
