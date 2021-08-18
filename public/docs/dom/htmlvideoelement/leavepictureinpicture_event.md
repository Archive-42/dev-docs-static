# HTMLVideoElement: leavepictureinpicture event

The `leavepictureinpicture` event is fired when the [`HTMLVideoElement`](../htmlvideoelement) leaves picture-in-picture mode successfully.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../pictureinpictureevent"><code>PictureInPictureEvent</code></a></td></tr><tr class="even"><td>Target</td><td><a href="../htmlvideoelement"><code>HTMLVideoElement</code></a></td></tr><tr class="odd"><td>Default Action</td><td>None</td></tr><tr class="even"><td>Event handler property</td><td><a href="onleavepictureinpicture"><code>HTMLVideoElement.onleavepictureinpicture</code></a></td></tr></tbody></table>

## Examples

These examples add an event listener for the HTMLVideoElement's `leavepictureinpicture` event, then post a message when that event handler has reacted to the event firing.

Using `addEventListener()`:

    const video = document.querySelector('#video');
    const button = document.querySelector('#button');

    function onExitPip() {
      console.log("Picture-in-Picture mode deactivated!");
    }

    video.addEventListener("leavepictureinpicture", onExitPip, false);

    button.onclick = function() => {
      if (document.pictureInPictureElement) {
        document.exitPictureInPicture();
      }
    }

Using the `onleavepictureinpicture` event handler property:

    const video = document.querySelector('#video');
    const button = document.querySelector('#button');

    function onExitPip() {
      console.log("Picture-in-Picture mode deactivated!");
    }

    video.onleavepictureinpicture = onExitPip;

    button.onclick = function() => {
      if (document.pictureInPictureElement) {
        document.exitPictureInPicture();
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/picture-in-picture/#eventdef-htmlvideoelement-leavepictureinpicture">Picture-in-Picture API<br />
<span class="small">The definition of 'leavepictureinpicture event' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td></tr></tbody></table>

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

`leavepictureinpicture_event`

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

- [`HTMLVideoElement`](../htmlvideoelement)
- [`Picture-in-Picture_API`](../picture-in-picture_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/leavepictureinpicture_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/leavepictureinpicture_event</a>
