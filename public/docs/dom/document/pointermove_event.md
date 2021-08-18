# Document: pointermove event

The `pointermove` event is fired when a pointer changes coordinates, and the pointer has not been [canceled](../htmlelement/pointercancel_event) by a browser [touch-action](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action).

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../pointerevent"><code>PointerEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onpointermove"><code>onpointermove</code></a></td></tr></tbody></table>

## Examples

Using `addEventListener()`:

    document.addEventListener('pointermove', (event) => {
      console.log('Pointer moved');
    });

Using the `onpointermove` event handler property:

    document.onpointermove = (event) => {
      console.log('Pointer moved');
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#the-pointermove-event">Pointer Events – Level 2</a></td><td><span class="spec-rec">Recommendation</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#the-pointermove-event">Pointer Events</a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

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

`pointermove_event`

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
- [`pointerup`](pointerup_event)
- [`pointercancel`](pointercancel_event)
- [`pointerout`](pointerout_event)
- [`pointerleave`](pointerleave_event)
- [`onpointerout`](../globaleventhandlers/onpointerout) event handler property
- This event on `HTMLElement` targets: [`pointermove`](../htmlelement/pointermove_event) event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/pointermove_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/pointermove_event</a>
