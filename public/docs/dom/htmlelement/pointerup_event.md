# HTMLElement: pointerup event

The `pointerup` event is fired when a pointer is no longer active.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../pointerevent"><code>PointerEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onpointerup</code></td></tr></tbody></table>

## Examples

Using `addEventListener()`:

    const para = document.querySelector('p');

    para.addEventListener('pointerup', (event) => {
      console.log('Pointer up');
    });

Using the `onpointerup` event handler property:

    const para = document.querySelector('p');

    para.onpointerup = (event) => {
      console.log('Pointer up');
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#the-pointerup-event">Pointer Events – Level 2</a></td><td><span class="spec-rec">Recommendation</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#the-pointerup-event">Pointer Events</a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

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

`pointerup_event`

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
- `pointerenter`
- `pointerdown`
- `pointermove`
- `pointercancel`
- `pointerout`
- `pointerleave`
- `onpointerup` event handler property
- This event on `Document` targets: `pointerup`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerup_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerup_event</a>
