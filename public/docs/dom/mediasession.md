# MediaSession

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `MediaSession` interface of the [Media Session API](media_session_api) allows a web page to provide custom behaviors for standard media playback interactions, and to report metadata that can be sent by the user agent to the device or operating system for presentation in standardized user interface elements.

For example, a smartphone might have a standard panel in its lock screen that provides controls for media playback and information display. A browser on the device can use `MediaSession` to make browser playback controllable from that standard/global user interface.

## Properties

[`metadata`](mediasession/metadata)  
Returns an instance of [`MediaMetadata`](mediametadata), which contains rich media metadata for display in a platform UI.

[`playbackState`](mediasession/playbackstate)  
Indicates whether the current media session is playing. Valid values are `none`, `paused`, or `playing`.

## Methods

[`setActionHandler()`](mediasession/setactionhandler)  
Sets an action handler for a [media session action](mediasessionaction), such as play or pause.

[`setPositionState()`](mediasession/setpositionstate)  
Sets the current playback position and speed of the media currently being presented.

## Examples

The following example creates a new media session and assigns action handlers to it:

    if ('mediaSession' in navigator) {
      navigator.mediaSession.metadata = new MediaMetadata({
        title: 'Unforgettable',
        artist: 'Nat King Cole',
        album: 'The Ultimate Collection (Remastered)',
        artwork: [
          { src: 'https://dummyimage.com/96x96',   sizes: '96x96',   type: 'image/png' },
          { src: 'https://dummyimage.com/128x128', sizes: '128x128', type: 'image/png' },
          { src: 'https://dummyimage.com/192x192', sizes: '192x192', type: 'image/png' },
          { src: 'https://dummyimage.com/256x256', sizes: '256x256', type: 'image/png' },
          { src: 'https://dummyimage.com/384x384', sizes: '384x384', type: 'image/png' },
          { src: 'https://dummyimage.com/512x512', sizes: '512x512', type: 'image/png' },
        ]
      });

      navigator.mediaSession.setActionHandler('play', function() { /* Code excerpted. */ });
      navigator.mediaSession.setActionHandler('pause', function() { /* Code excerpted. */ });
      navigator.mediaSession.setActionHandler('stop', function() { /* Code excerpted. */ });
      navigator.mediaSession.setActionHandler('seekbackward', function() { /* Code excerpted. */ });
      navigator.mediaSession.setActionHandler('seekforward', function() { /* Code excerpted. */ });
      navigator.mediaSession.setActionHandler('seekto', function() { /* Code excerpted. */ });
      navigator.mediaSession.setActionHandler('previoustrack', function() { /* Code excerpted. */ });
      navigator.mediaSession.setActionHandler('nexttrack', function() { /* Code excerpted. */ });
      navigator.mediaSession.setActionHandler('skipad', function() { /* Code excerpted. */ });
    }

The following example sets up two functions for playing and pausing, then uses them as callbacks with the relevant action handlers.

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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#the-mediasession-interface">Media Session Standard<br />
<span class="small">The definition of 'MediaSession' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`MediaSession`

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

`metadata`

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

`setActionHandler`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSession" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSession</a>
