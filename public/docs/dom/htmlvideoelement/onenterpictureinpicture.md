# HTMLVideoElement.onenterpictureinpicture

The `onenterpictureinpicture` property of the [`HTMLVideoElement`](../htmlvideoelement) interface is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes [`HTMLVideoElement.enterpictureinpicture`](enterpictureinpicture_event) events.

The `enterpictureinpicture` event fires after the video has successfully entered picture-in-picture mode.

## Syntax

    video.onenterpictureinpicture = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`FocusEvent`](../focusevent) object as its sole argument.

## Examples

### Window size logger

    <button id="button>Enter Picture-in-Picture</button>
    <video id="video" muted autoplay src=""></video>

    const video = document.querySelector('#video');
    const button = document.querySelector('#button');

    function onEnterPip() {
      console.log("Picture-in-Picture mode activated!");
    }

    video.onenterpictureinpicture = onEnterPip;

    button.onclick = function() => {
      video.requestPictureInPicture();
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/picture-in-picture/#dom-htmlvideoelement-onenterpictureinpicture">Picture-in-Picture API<br />
<span class="small">The definition of 'HTMLVideoElement.onenterpictureinpicture' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`onenterpictureinpicture`

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

- [`Picture-in-Picture_API`](../picture-in-picture_api)
- [`HTMLVideoElement`](../htmlvideoelement)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/onenterpictureinpicture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/onenterpictureinpicture</a>
