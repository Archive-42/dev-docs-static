HTMLVideoElement.requestPictureInPicture()
==========================================

The **[`HTMLVideoElement`](../htmlvideoelement)** method `requestPictureInPicture()` issues an asynchronous request to display the video in picture-in-picture mode.

It's not guaranteed that the video will be put into picture-in-picture. If permission to enter that mode is granted, the returned [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) will resolve and the video will receive a `enterpictureinpicture` event to let it know that it's now in picture-in-picture.

Syntax
------

    videoElement.requestPictureInPicture();

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that will resolve to a [`PictureInPictureWindow`](../pictureinpicturewindow) object. that can be used to listen when a user will resize that floating window.

Examples
--------

This example requests that the video enters Picture-in-Picture mode, and sets an event listener to handle the floating window resizing.

    function enterPictureInPicture() {
      videoElement.requestPictureInPicture()
        .then(pictureInPictureWindow => {
          pictureInPictureWindow.addEventListener("resize", () => onPipWindowResize(), false);
        })
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/picture-in-picture/#request-pip">Picture-in-Picture API<br />
<span class="small">The definition of 'HTMLVideoElement.requestPictureInPicture()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`requestPictureInPicture`

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

See also
--------

-   The [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element
-   [`HTMLVideoElement.autoPictureInPicture`](autopictureinpicture)
-   [`HTMLVideoElement.disablePictureInPicture`](disablepictureinpicture)
-   [`Document.pictureInPictureEnabled`](../document/pictureinpictureenabled)
-   [`Document.exitPictureInPicture()`](../document/exitpictureinpicture)
-   [`Document.pictureInPictureElement`](../document/pictureinpictureelement)
-   [`:picture-in-picture`](https://developer.mozilla.org/en-US/docs/Web/CSS/:picture-in-picture)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/requestPictureInPicture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/requestPictureInPicture</a>
