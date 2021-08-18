# Document.exitPictureInPicture()

The [`Document`](../document) method `exitPictureInPicture()` requests that a video contained in this document, which is currently floating, be taken out of picture-in-picture mode, restoring the previous state of the screen. This usually reverses the effects of a previous call to [`HTMLVideoElement.requestPictureInPicture()`](../htmlvideoelement/requestpictureinpicture).

## Syntax

    exitPromise = document.exitPictureInPicture();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), which is resolved once the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) has finished exiting picture-in-picture mode. If an error occurs while attempting to exit full-screen mode, the `catch()` handler for the promise is called.

## Examples

This example causes the current document to exit picture-in-picture mode whenever the mouse button is clicked within it.

    document.onclick = function (event) {
      if (document.pictureInPictureElement) {
        document.exitPictureInPicture()
          .then(() => console.log("Document Exited from Picture-in-Picture mode"))
          .catch((err) => console.error(err))
      } else {
        video.requestPictureInPicture();
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/picture-in-picture/#exit-pip">Picture-in-Picture API<br />
<span class="small">The definition of 'Document.exitPictureInPicture()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`exitPictureInPicture`

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
- [`Document.pictureInPictureElement`](pictureinpictureelement)
- [`:picture-in-picture`](https://developer.mozilla.org/en-US/docs/Web/CSS/:picture-in-picture)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/exitPictureInPicture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/exitPictureInPicture</a>
