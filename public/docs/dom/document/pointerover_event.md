# Document: pointerover event

The `pointerover` event is fired when a pointing device is moved into an element's hit test boundaries.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../pointerevent"><code>PointerEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onpointerover"><code>onpointerover</code></a></td></tr></tbody></table>

## Examples

Using `addEventListener()`:

    document.addEventListener('pointerover', (event) => {
      console.log('Pointer moved in');
    });

Using the `onpointerover` event handler property:

    document.onpointerover = (event) => {
      console.log('Pointer moved in');
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#the-pointerover-event">Pointer Events – Level 2</a></td><td><span class="spec-rec">Recommendation</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#the-pointerover-event">Pointer Events</a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

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

`pointerover_event`

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
- [`pointerenter`](pointerenter_event)
- [`pointerdown`](pointerdown_event)
- [`pointermove`](pointermove_event)
- [`pointercancel`](pointercancel_event)
- [`pointerout`](pointerout_event)
- [`pointerleave`](pointerleave_event)
- [`onpointerover`](../globaleventhandlers/onpointerover) event handler property
- This event on `HTMLElement` targets: [`pointerover`](../htmlelement/pointerover_event) event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerover_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/pointerover_event</a>
