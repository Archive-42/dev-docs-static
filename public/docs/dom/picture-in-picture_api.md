Picture-in-Picture API
======================

The **Picture-in-Picture API** allow websites to create a floating video window always on top of other windows so that users may continue consuming media while they interact with other content sites, or applications on their device.

Interfaces
----------

[`PictureInPictureWindow`](pictureinpicturewindow)  
Represents the floating video window; contains [`width`](pictureinpicturewindow/width) and [`height`](pictureinpicturewindow/height) properties, and an [`onresize`](pictureinpicturewindow/onresize) event handler property.

Methods
-------

The Picture-in-Picture API adds methods to the [`HTMLVideoElement`](htmlvideoelement) and [`Document`](document) interfaces to allow toggling of the floating video window.

### Methods on the HTMLVideoElement interface

[`HTMLVideoElement.requestPictureInPicture()`](htmlvideoelement/requestpictureinpicture)  
Requests that the user agent enters the video into picture-in-picture mode

### Methods on the Document interface

[`Document.exitPictureInPicture()`](document/exitpictureinpicture)  
Requests that the user agent returns the element in picture-in-picture mode back into its original box.

Properties
----------

*The Picture-in-Picture API augments the* [`HTMLVideoElement`](htmlvideoelement), [`Document`](document), and [`ShadowRoot`](shadowroot) *interfaces with properties that can be used to determine if the floating video window mode is supported and available, if picture-in-picture mode is currently active, and which video is floating.*

### Properties on the HTMLVideoElement interface

[`HTMLVideoElement.autoPictureInPicture`](htmlvideoelement/autopictureinpicture)  
The `autoPictureInPicture` property will automatically enter and leave the picture-in-picture mode for a video element when the user switches tab and/or applications.

[`HTMLVideoElement.disablePictureInPicture`](htmlvideoelement/disablepictureinpicture)  
The `disablePictureInPicture` property will provide a hint to the user agent to not suggest the picture-in-picture to users or to request it automatically.

### Properties on the Document interface

[`Document.pictureInPictureEnabled`](document/pictureinpictureenabled)  
The `pictureInPictureEnabled` property tells you whether or not it is possible to engage picture-in-picture mode. This is `false` if picture-in-picture mode is not available for any reason (e.g. the [`"picture-in-picture"` feature](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Feature-Policy/picture-in-picture) has been disallowed, or picture-in-picture mode is not supported).

### Properties on the Document or ShadowRoot interfaces

 [`Document.pictureInPictureElement`](document/pictureinpictureelement) / [`ShadowRoot.pictureInPictureElement`](shadowroot/pictureinpictureelement)   
The `pictureInPictureElement` property tells you which [`Element`](element) is currently being displayed in the floating window (or in the shadow DOM). If this is `null`, the document (or shadow DOM) has no node currently in picture-in-picture mode.

Events
------

*The Picture-in-Picture API defines three events, which can be used to detect when picture-in-picture mode is toggled and when the floating video window is resized.*

[`enterpictureinpicture`](htmlvideoelement/enterpictureinpicture_event)  
Sent to a [`HTMLVideoElement`](htmlvideoelement) when it enters picture-in-picture mode. The associated event handler is [`HTMLVideoElement.onenterpictureinpicture`](htmlvideoelement/onenterpictureinpicture)

[`leavepictureinpicture`](htmlvideoelement/leavepictureinpicture_event)  
Sent to a [`HTMLVideoElement`](htmlvideoelement) when it leaves picture-in-picture mode. The associated event handler is [`HTMLVideoElement.onleavepictureinpicture`](htmlvideoelement/onleavepictureinpicture)

[`resize`](pictureinpicturewindow/resize_event)  
Sent to a [`PictureInPictureWindow`](pictureinpicturewindow) when it changes size. The associated event handler is [`PictureInPictureWindow.onresize`](pictureinpicturewindow/onresize)

Controlling styling
-------------------

The `:picture-in-picture` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) matches the video element currently in picture-in-picture mode, allowing you to configure your stylesheets to automatically adjust the size, style, or layout of content when a video switches back and forth between picture-in-picture and traditional presentation modes.

Controlling access
------------------

The availability of picture-in-picture mode can be controlled using [Feature Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy). The full-screen mode feature is identified by the string `"picture-in-picture"`, with a default allow-list value of `"self"`, meaning that picture-in-picture mode is permitted in top-level document contexts, as well as to nested browsing contexts loaded from the same origin as the top-most document.

See [Using Feature Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Feature_Policy/Using_Feature_Policy) to learn more about using Feature Policy to control access to an API.

Examples
--------

In this example, a video is presented in a web page. Clicking the button below lets the user toggle the floating video window.

### Toggling picture-in-picture mode

This code is called by a click handler when the user clicks the "<span class="pl-s">Toggle Picture-in-Picture</span>" button:

    function togglePictureInPicture() {
      if (document.pictureInPictureElement) {
          document.exitPictureInPicture();
      } else {
        if (document.pictureInPictureEnabled) {
          video.requestPictureInPicture();
        }
      }
    }

This block starts by looking at the value of the [`document`](document)'s `pictureInPictureElement` attribute. If the value is `null`, no video is in the floating window. so we can request a video to enter the picture-in-picture mode; otherwise, it's the element that's currently in picture-in-picture mode. Switching to picture-in-picture mode is done by calling [`HTMLVideoElement.requestPictureInPicture()`](htmlvideoelement/requestpictureinpicture) on the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element.

If a video is in the floating window (`pictureInPictureElement` is not `null`), we call [`exitPictureInPicture()`](document/exitpictureinpicture) on the `document` to bring the video back into its initial box.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/picture-in-picture/">Picture-in-Picture API</a></td><td><span class="spec-draft">Draft</span></td></tr></tbody></table>

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

`Picture-in-Picture_API`

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

`Picture-in-Picture_API`

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

`Picture-in-Picture_API`

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

`Picture-in-Picture_API`

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

`Picture-in-Picture_API`

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

`Picture-in-Picture_API`

No

No

No

No

No

13.1

No

No

No

No

13.4

No

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

`Picture-in-Picture_API`

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

BCD tables only load in the browser

### HTMLVideoElement.autoPictureInPicture

BCD tables only load in the browser

### HTMLVideoElement.disablePictureInPicture

BCD tables only load in the browser

### Document.pictureInPictureEnabled

BCD tables only load in the browser

### Document.exitPictureInPicture

BCD tables only load in the browser

### Document.pictureInPictureElement

BCD tables only load in the browser

### PictureInPictureWindow

BCD tables only load in the browser

See also
--------

-   [`HTMLVideoElement.requestPictureInPicture()`](htmlvideoelement/requestpictureinpicture)
-   [`HTMLVideoElement.autoPictureInPicture`](htmlvideoelement/autopictureinpicture)
-   [`HTMLVideoElement.disablePictureInPicture`](htmlvideoelement/disablepictureinpicture)
-   [`Document.pictureInPictureEnabled`](document/pictureinpictureenabled)
-   [`Document.exitPictureInPicture()`](document/exitpictureinpicture)
-   [`Document.pictureInPictureElement`](document/pictureinpictureelement)
-   [`:picture-in-picture`](https://developer.mozilla.org/en-US/docs/Web/CSS/:picture-in-picture)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Picture-in-Picture_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Picture-in-Picture_API</a>
