# HTMLElement: pointerenter event

The `pointerenter` event fires when a pointing device is moved into the hit test boundaries of an element or one of its descendants, including as a result of a `pointerdown` event from a device that does not support hover (see `pointerdown`).

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../pointerevent"><code>PointerEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onpointerenter</code></td></tr></tbody></table>

## Examples

Using `addEventListener()`:

    const para = document.querySelector('p');

    para.addEventListener('pointerenter', (event) => {
      console.log('Pointer entered element');
    });

Using the `onpointerenter` event handler property:

    const para = document.querySelector('p');

    para.onpointerenter = (event) => {
      console.log('Pointer entered element');
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#the-pointerenter-event">Pointer Events – Level 2</a></td><td><span class="spec-rec">Recommendation</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#the-pointerenter-event">Pointer Events</a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

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

`pointerenter_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

## See also

- `gotpointercapture`
- `lostpointercapture`
- `pointerover`
- `pointerdown`
- `pointermove`
- `pointerup`
- `pointercancel`
- `pointerout`
- `pointerleave`
- `onpointerenter` event handler property
- This event on `Document` targets: `pointerenter` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerenter_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerenter_event</a>
