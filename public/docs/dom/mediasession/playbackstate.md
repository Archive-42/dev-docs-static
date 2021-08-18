MediaSession.playbackState
==========================

The `playbackState` property of the [`MediaSession`](../mediasession) interface indicates whether the current media session is playing or paused.

Syntax
------

    let playbackState = mediaSession.playbackState;
    mediaSession.playbackState = playbackState;

### Value

A [`DOMString`](../domstring) indicating the current playback state of the media session. The value may be one of the following:

`none`  
The browsing context doesn't currently know the current playback state, or the playback state is not available at this time.

`paused`  
The browser's media session is currently paused. Playback may be resumed.

`playing`  
The browser's media session is currently playing media, which can be paused.

Example
-------

The following example sets up two functions for playing and pausing, then uses them as callbacks with the relevant action handlers. Each function harnesses the `playbackState` property to indicate whether the audio is playing or paused.

    const actionHandlers = [
      // play
      [
        'play',
        async function() {
          // play our audio
          await audioEl.play();
          // set playback state
          navigator.mediaSession.playbackState = "playing";
          // update our status element
          updateStatus(allMeta[index], 'Action: play  |  Track is playing...')
        }
      ],
      [
        'pause',
        () => {
          // pause out audio
          audioEl.pause();
          // set playback state
          navigator.mediaSession.playbackState = "paused";
          // update our status element
          updateStatus(allMeta[index], 'Action: pause  |  Track has been paused...');
        }
      ],
    ]

    for (const [action, handler] of actionHandlers) {
      try {
        navigator.mediaSession.setActionHandler(action, handler);
      } catch (error) {
        console.log(`The media session action "${action}" is not supported yet.`);
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#dom-mediasession-playbackstate">Media Session Standard<br />
<span class="small">The definition of 'playbackState' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`playbackState`

73

79

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSession/playbackState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSession/playbackState</a>
