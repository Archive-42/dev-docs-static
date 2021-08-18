PictureInPictureWindow: resize event
====================================

The `resize` event fires when the floating video window has been resized.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../pictureinpicturewindow"><code>PictureInPictureWindow</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onresize"><code>onresize</code></a></td></tr></tbody></table>

Examples
--------

### Window size logger

    <p>Resize the floating video window to fire the <code>resize</code> event.</p>
    <p>Window height: <span id="height"></span></p>
    <p>Window width: <span id="width"></span></p>
    <video id="video" src="" muted autoplay></video>

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

### addEventListener equivalent

You could set up the event handler using the `addEventListener()` method:

    pictureInPictureWindow.addEventListener('resize', resize);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/picture-in-picture/#eventdef-pictureinpicturewindow-resize">Picture-in-Picture API<br />
<span class="small">The definition of 'resize' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td></tr></tbody></table>

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

See also
--------

-   [`PictureInPictureWindow.onresize`](onresize)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PictureInPictureWindow/resize_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PictureInPictureWindow/resize_event</a>
