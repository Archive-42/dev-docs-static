MediaMetadata.title
===================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `title` property of the [`MediaMetaData`](../mediametadata) interface returns or sets the title of the media to be played.

Syntax
------

    var title = mediaMetaData.title
    mediaMetaData.title = title

### Value

A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) containing the title of the media.

Examples
--------

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediasession/#dom-mediametadata-title">Media Session Standard<br />
<span class="small">The definition of 'title' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaMetadata/title" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaMetadata/title</a>
