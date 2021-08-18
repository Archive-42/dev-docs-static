HTMLVideoElement: enterpictureinpicture event
=============================================

The `enterpictureinpicture` event is fired when the [`HTMLVideoElement`](../htmlvideoelement) enters picture-in-picture mode successfully.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../pictureinpictureevent"><code>PictureInPictureEvent</code></a></td></tr><tr class="even"><td>Target</td><td><a href="../htmlvideoelement"><code>HTMLVideoElement</code></a></td></tr><tr class="odd"><td>Default Action</td><td>None</td></tr><tr class="even"><td>Event handler property</td><td><a href="onenterpictureinpicture"><code>HTMLVideoElement.onenterpictureinpicture</code></a></td></tr></tbody></table>

Examples
--------

These examples add an event listener for the HTMLVideoElement's `enterpictureinpicture` event, then post a message when that event handler has reacted to the event firing.

Using `addEventListener()`:

    const video = document.querySelector('#video');
    const button = document.querySelector('#button');

    function onEnterPip() {
      console.log("Picture-in-Picture mode activated!");
    }

    video.addEventListener('enterpictureinpicture', onEnterPip, false);

    button.onclick = function() => {
      video.requestPictureInPicture();
    }

Using the `onenterpictureinpicture` event handler property:

    const video = document.querySelector('#video');
    const button = document.querySelector('#button');

    function onEnterPip() {
      console.log("Picture-in-Picture mode activated!");
    }

    video.onenterpictureinpicture = onEnterPip;

    button.onclick = function() => {
      video.requestPictureInPicture();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/picture-in-picture/#eventdef-htmlvideoelement-enterpictureinpicture">Picture-in-Picture API<br />
<span class="small">The definition of 'enterpictureinpicture event' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td></tr></tbody></table>

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

`enterpictureinpicture_event`

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

-   [`HTMLVideoElement`](../htmlvideoelement)
-   [`Picture-in-Picture_API`](../picture-in-picture_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/enterpictureinpicture_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/enterpictureinpicture_event</a>
