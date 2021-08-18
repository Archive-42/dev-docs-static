# MediaMetadata

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `MediaMetadata` interface of the [Media Session API](media_session_api) allows a web page to provide rich media metadata for display in a platform UI.

## Constructor

[`MediaMetadata.MediaMetadata()`](mediametadata/mediametadata)  
Creates a new `MediaMetaData` object.

## Properties

[`MediaMetadata.title`](mediametadata/title)  
Returns or sets the title of the media to be played.

[`MediaMetadata.artist`](mediametadata/artist)  
Returns or sets the name of the artist, group, creator, etc. of the media to be played.

[`MediaMetadata.album`](mediametadata/album)  
Returns or sets the name of the album or collection containing the media to be played.

[`MediaMetadata.artwork`](mediametadata/artwork)  
Returns or sets an array of images associated with playing media.

## Examples

The following example checks for browser compatibility and sets the current metadata for the media session.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#the-mediametadata-interface">Media Session Standard<br />
<span class="small">The definition of 'MediaMetaData' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`MediaMetadata`

57

No

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

`MediaMetadata`

57

No

71

No

Yes

No

No

57

82

No

No

7.0

`album`

57

No

71

No

Yes

No

No

57

82

No

No

7.0

`artist`

57

No

71

No

Yes

No

No

57

82

No

No

7.0

`artwork`

57

No

71

No

Yes

No

No

57

82

No

No

7.0

`title`

57

No

71

No

Yes

No

No

57

82

No

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaMetadata" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaMetadata</a>
