# PictureInPictureWindow

The `PictureInPictureWindow` interface represents an object able to programmatically obtain the `width` and `height` and `resize event` of the floating video window.

An object with this interface is obtained using the [`HTMLVideoElement.requestPictureInPicture()`](htmlvideoelement/requestpictureinpicture) promise return value.

## Properties

_The `PictureInPictureWindow` interface doesn't inherit any properties._

[`PictureInPictureWindow.width`](pictureinpicturewindow/width) <span class="badge inline readonly">Read only </span>  
Determines the width of the floating video window.

[`PictureInPictureWindow.height`](pictureinpicturewindow/height) <span class="badge inline readonly">Read only </span>  
Determines the height of the floating video window.

## Methods

_The `PictureInPictureWindow` interface doesn't inherit any methods._

## Events

_The `PictureInPictureWindow` interface doesn't inherit any events._

[`PictureInPictureWindow.resize`](pictureinpicturewindow/resize_event)  
Sent to a [`PictureInPictureWindow`](pictureinpicturewindow) when the floating video window is resized. The associated event handler is [`PictureInPictureWindow.onresize`](pictureinpicturewindow/onresize).

## Examples

Given a `<button>` and a `<video>`, clicking the button will make the video enter the picture-in-picture mode; we then attach an event to print the floating video window dimensions to the console.

    const button = document.querySelector("button");
    const video = document.querySelector("video");

    function printPipWindowDimensions(evt) {
      const pipWindow = evt.target;
      console.log(`The floating window dimensions are: ${pipWindow.width}x${pipWindow.height}px`);
      // will print:
      // The floating window dimensions are: 640x360px
    }

    button.onclick = function() {
      video.requestPictureInPicture().then(pictureInPictureWindow => {
        pictureInPictureWindow.onresize = printPipWindowDimensions;
      });
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/picture-in-picture/#pictureinpicturewindow">Picture-in-Picture API</a></td><td><span class="spec-draft">Draft</span></td><td>Initial specification.</td></tr></tbody></table>

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

`PictureInPictureWindow`

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

`height`

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

`onresize`

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

`resize_event`

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

`width`

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

- [`Picture-in-Picture_API`](picture-in-picture_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PictureInPictureWindow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PictureInPictureWindow</a>
