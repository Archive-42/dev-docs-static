# Document.pictureInPictureEnabled

The read-only `pictureInPictureEnabled` property of the [`Document`](../document) interface indicates whether or not picture-in-picture mode is available. Picture-in-Picture mode is available by default unless specified otherwise by a [Feature-Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/picture-in-picture).

Although this property is read-only, it will not throw if it is modified (even in strict mode); the setter is a no-operation and will be ignored.

## Syntax

    let isPictureInPictureAvailable = document.pictureInPictureEnabled;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value, which is `true` if a video can enter picture-in-picture and be displayed in a floating window by calling <span class="page-not-created">`HTMLVideoElement.requestFullscreen()`</span>. If picture-in-picture mode isn't available, this value is `false`.

## Examples

In this example, before attempting to enter picture-in-picture mode for a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element the value of `pictureInPictureEnabled` is checked, in order to avoid making the call if the feature is not available.

    function requestPictureInPicture() {
      if (document.pictureInPictureEnabled) {
        videoElement.requestPictureInPicture();
      } else {
        console.log('Your browser cannot use picture-in-picture right now');
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/picture-in-picture/#dom-document-pictureinpictureenabled">Picture-in-Picture API<br />
<span class="small">The definition of 'Document.pictureInPictureEnabled' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`pictureInPictureEnabled`

69

79

No

No

56

13.1

No

No

No

No

13.4

No

## See also

- [`HTMLVideoElement.requestPictureInPicture()`](../htmlvideoelement/requestpictureinpicture)
- [`HTMLVideoElement.autoPictureInPicture`](../htmlvideoelement/autopictureinpicture)
- [`HTMLVideoElement.disablePictureInPicture`](../htmlvideoelement/disablepictureinpicture)
- [`Document.exitPictureInPicture()`](exitpictureinpicture)
- [`Document.pictureInPictureElement`](pictureinpictureelement)
- [`:picture-in-picture`](https://developer.mozilla.org/en-US/docs/Web/CSS/:picture-in-picture)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/pictureInPictureEnabled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/pictureInPictureEnabled</a>
