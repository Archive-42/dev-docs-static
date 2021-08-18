# MediaSession.metadata

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `metadata` property of the [`MediaSession`](../mediasession) interface contains a [`MediaMetadata`](../mediametadata) object providing descriptive information about the currently playing media, or `null` if the metadata has not been set. This metadata is provided by the browser to the device for presentation in any standard media control user interface the device might offer.

## Syntax

    var mediaMetadata = navigator.mediaSession.metadata;
    navigator.mediaSession.metadata = mediaMetadata;

### Value

An instance of [`MediaMetadata`](../mediametadata) containing information about the media currently being played.

## Example

The following example checks for compatibility and creates a new media session with the relevant metadata:

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

    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#dom-mediasession-metadata">Media Session Standard<br />
<span class="small">The definition of 'MediaSession.metadata' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaSession/metadata" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaSession/metadata</a>
