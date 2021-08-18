# Document: pointerleave event

The `pointerleave` event is fired when a pointing device is moved out of the hit test boundaries of an element. For pen devices, this event is fired when the stylus leaves the hover range detectable by the digitizer.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../pointerevent"><code>PointerEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onpointerleave"><code>onpointerleave</code></a></td></tr></tbody></table>

## Examples

Using `addEventListener()`:

    document.addEventListener('pointerleave', (event) => {
      console.log('Pointer left element');
    });

Using the `onpointerleave` event handler property:

    document.onpointerleave = (event) => {
      console.log('Pointer left element');
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#the-pointerleave-event">Pointer Events – Level 2</a></td><td><span class="spec-rec">Recommendation</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#the-pointerleave-event">Pointer Events</a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

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

`pointerleave_event`

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

- [`gotpointercapture`](gotpointercapture_event)
- [`lostpointercapture`](lostpointercapture_event)
- [`pointerover`](pointerover_event)
- [`pointerenter`](pointerenter_event)
- [`pointerdown`](pointerdown_event)
- [`pointermove`](pointermove_event)
- [`pointerup`](pointerup_event)
- [`pointercancel`](pointercancel_event)
- [`pointerout`](pointerout_event)
- [`onpointerleave`](../globaleventhandlers/onpointerleave) event handler property
- This event on `HTMLElement` targets: [`pointerleave`](../htmlelement/pointerleave_event) event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerleave_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerleave_event</a>
