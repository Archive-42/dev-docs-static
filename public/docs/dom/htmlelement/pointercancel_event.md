# HTMLElement: pointercancel event

The `pointercancel` event is fired when the browser determines that there are unlikely to be any more pointer events, or if after the `pointerdown` event is fired, the pointer is then used to manipulate the viewport by panning, zooming, or scrolling.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../pointerevent"><code>PointerEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onpointercancel</code></td></tr></tbody></table>

Some examples of situations that will trigger a `pointercancel` event:

- A hardware event occurs that cancels the pointer activities. This may include, for example, the user switching applications using an application switcher interface or the "home" button on a mobile device.
- The device's screen orientation is changed while the pointer is active.
- The browser decides that the user started pointer input accidentally. This can happen if, for example, the hardware supports palm rejection to prevent a hand resting on the display while using a stylus from accidentally triggering events.
- The [`touch-action`](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action) CSS property prevents the input from continuing.

After the `pointercancel` event is fired, the browser will also send `pointerout` followed by `pointerleave`.

## Examples

Using `addEventListener()`:

    const para = document.querySelector('p');

    para.addEventListener('pointercancel', (event) => {
      console.log('Pointer event cancelled');
    });

Using the `onpointercancel` event handler property:

    const para = document.querySelector('p');

    para.onpointercancel = (event) => {
      console.log('Pointer event cancelled');
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#the-pointercancel-event">Pointer Events – Level 2</a></td><td><span class="spec-rec">Recommendation</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#the-pointercancel-event">Pointer Events</a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

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

`pointercancel_event`

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

- Related events
  - `gotpointercapture`
  - `lostpointercapture`
  - `pointerover`
  - `pointerenter`
  - `pointerdown`
  - `pointermove`
  - `pointerup`
  - `pointerout`
  - `pointerleave`
- `onpointercancel` event handler property
- This event on `Document` targets: `pointercancel` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointercancel_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointercancel_event</a>
