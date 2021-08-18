# Document.pictureInPictureElement

The `Document.pictureInPictureElement` read-only property returns the [`Element`](../element) that is currently being presented in picture-in-picture mode in this document, or `null` if picture-in-picture mode is not currently in use.

Although this property is read-only, it will not throw if it is modified (even in strict mode); the setter is a no-operation and will be ignored.

## Syntax

    document.pictureInPictureElement;

### Return value

A reference to the [`Element`](../element) object that's currently in picture-in-picture mode; if picture-in-picture mode isn't currently in use by the `document`, the returned value is `null`.

## Examples

This example presents a function, `exitPictureInPicture()`, which tests the value returned by `pictureInPictureElement`. If the document is in picture-in-picture mode (`pictureInPictureElement` isn't `null`), `Document.exitPictureInPicture()` is run to exit picture-in-picture mode.

    function exitPictureInPicture() {
      if (document.pictureInPictureElement) {
        document.exitPictureInPicture();
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/picture-in-picture/#dom-documentorshadowroot-pictureinpictureelement">Picture-in-Picture API<br />
<span class="small">The definition of 'Document.pictureInPictureElement' in that specification.</span></a></td></tr></tbody></table>

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

`pictureInPictureElement`

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
- [`Document.pictureInPictureEnabled`](pictureinpictureenabled)
- [`Document.exitPictureInPicture()`](exitpictureinpicture)
- [`:picture-in-picture`](https://developer.mozilla.org/en-US/docs/Web/CSS/:picture-in-picture)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/pictureInPictureElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/pictureInPictureElement</a>
