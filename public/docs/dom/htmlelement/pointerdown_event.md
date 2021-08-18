# HTMLElement: pointerdown event

The `pointerdown` event is fired when a pointer becomes active. For mouse, it is fired when the device transitions from no buttons depressed to at least one button depressed. For touch, it is fired when physical contact is made with the digitizer. For pen, it is fired when the stylus makes physical contact with the digitizer.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../pointerevent"><code>PointerEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onpointerdown</code></td></tr></tbody></table>

## Examples

Using `addEventListener()`:

    const para = document.querySelector('p');

    para.addEventListener('pointerdown', (event) => {
      console.log('Pointer down event');
    });

Using the `onpointerdown` event handler property:

    const para = document.querySelector('p');

    para.onpointerdown = (event) => {
      console.log('Pointer down event');
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#the-pointerdown-event">Pointer Events – Level 2</a></td><td><span class="spec-rec">Recommendation</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#the-pointerdown-event">Pointer Events</a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

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

`pointerdown_event`

55

12

12-79

59

29

11

10

42

No

55

55

79

29

42

No

6.0

## See also

- `onpointerdown` event handler property.
- This event on `Document` targets: `pointerdown` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerdown_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerdown_event</a>
