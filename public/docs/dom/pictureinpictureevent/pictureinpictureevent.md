# PictureInPictureEvent()

The `PictureInPictureEvent()` constructor returns a newly created [`PictureInPictureEvent`](../pictureinpictureevent) object with an optional [`EventTarget`](../eventtarget). When the event has both a source and a destination, the `relatedTarget` value must be set to the other target.

## Syntax

    var pictureInPictureEvent = new PictureInPictureEvent(typeArg[, pictureInPictureInit]);

### Properties

_The `PictureInPictureEvent()` constructor also inherits arguments from [`Event()`](../event/event)._

`typeArg`  
Is a [`DOMString`](../domstring) representing the name of the event.

`focusEventInit` <span class="badge inline optional">Optional</span>  
Is a `PictureInPictureEventInit` dictionary, having the following fields:

- `"relatedTarget"`, optional and defaulting to `null`, is an [`EventTarget`](../eventtarget).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/picture-in-picture/#dom-pictureinpictureevent-pictureinpictureevent">Picture-in-Picture API<br />
<span class="small">The definition of 'PictureInPictureEvent()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`PictureInPictureEvent`

85

69-85

85

79-85

No

No

71

56-71

13.1

No

No

No

No

13.4

No

## See also

- The [`PictureInPictureEvent`](../pictureinpictureevent) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PictureInPictureEvent/PictureInPictureEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PictureInPictureEvent/PictureInPictureEvent</a>
