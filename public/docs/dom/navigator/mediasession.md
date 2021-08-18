Navigator.mediaSession
======================

The read-only [`Navigator`](../navigator) property `mediaSession` returns a [`MediaSession`](../mediasession) object that can be used to share with the browser metadata and other information about the current playback state of media being handled by a document. This information may, in turn, be shared with the device and/or operating system in order to a device's standard media control user experience to describe and control the playback of the media.

In addition, the `MediaSession` interface provides the [`setActionHandler()`](../mediasession/setactionhandler) method, which lets you receive events when the user engages device controls such as either onscreen or physical play, pause, seek, and other similar controls. An internet radio app, for example, can use `setActionHandler()` to let fhe media controls on a keyboard or elsewhere on the user's device be used to control the app's media playback.

Syntax
------

    let mediaSession = navigator.mediaSession;

### Value

A [`MediaSession`](../mediasession) object the current document can use to share information about media it's playing and its current playback status. This information can include typical metadata such as the title, artist, and album name of the song being played as well as potentially one or more images containing things like album art, artist photos, and so forth.

Example
-------

In this example, metadata is submitted to the `mediaSession` object. Note that the code begins by ensuring that the [`navigator.mediaSession`](mediasession) property is available before attempting to use it.

    if ("mediaSession" in navigator){
      navigator.mediaSession.metadata = new MediaMetadata({
        title: "Podcast Episode Title",
        artist: "Podcast Host",
        album: "Podcast Name",
        artwork: [{src: "podcast.jpg"}]
      });
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#dom-navigator-mediasession">Media Session Standard<br />
<span class="small">The definition of 'navigator.mediaSession' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`mediaSession`

73

79

82

71

No

No

No

No

57

82

No

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaSession" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/mediaSession</a>
