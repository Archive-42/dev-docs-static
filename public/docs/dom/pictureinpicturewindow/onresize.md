PictureInPictureWindow.onresize
===============================

The `onresize` property of the [`PictureInPictureWindow`](../pictureinpicturewindow) interface is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes [`PictureInPictureWindow.resize`](resize_event) events.

The `resize` event fires after the floating video window has been resized.

Syntax
------

    pictureInPictureWindow.onresize = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`FocusEvent`](../focusevent) object as its sole argument.

Examples
--------

### Window size logger

    <p>Resize the floating video window to fire the <code>resize</code> event.</p>
    <p>Window height: <span id="height"></span></p>
    <p>Window width: <span id="width"></span></p>
    <video id="video" muted autoplay src=""></video>

    const video = document.querySelector('#video');
    const heightOutput = document.querySelector('#height');
    const widthOutput = document.querySelector('#width');

    function resize(evt) {
      heightOutput.textContent = evt.target.width;
      widthOutput.textContent = evt.target.width;
    }

    video.requestPictureInPicture()
      .then(pictureInPictureWindow => {
        pictureInPictureWindow.onresize = resize;
      });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/picture-in-picture/#dom-pictureinpicturewindow-onresize">Picture-in-Picture API<br />
<span class="small">The definition of 'PictureInPictureWindow.onresize' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

See also
--------

-   [Picture-in-Picture API](../picture-in-picture_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PictureInPictureWindow/onresize" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PictureInPictureWindow/onresize</a>
