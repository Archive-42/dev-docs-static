# Document: gotpointercapture event

The `gotpointercapture` event is fired when an element captures a pointer using [`setPointerCapture()`](../element/setpointercapture).

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../pointerevent"><code>PointerEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/ongotpointercapture"><code>ongotpointercapture</code></a></td></tr></tbody></table>

## Examples

This example gets a `<p>` element and listens for the `gotpointercapture` event. It then calls `setPointerCapture()` on the element on a `pointerdown` event, which will trigger `gotpointercapture`.

    const para = document.querySelector('p');

    document.addEventListener('gotpointercapture', () => {
      console.log('I\'ve been captured!')
    });

    para.addEventListener('pointerdown', (event) => {
      para.setPointerCapture(event.pointerId);
    });

The same example, using the `ongotpointercapture` event handler property:

    const para = document.querySelector('p');

    document.ongotpointercapture = () => {
      console.log('I\'ve been captured!')
    };

    para.addEventListener('pointerdown', (event) => {
      para.setPointerCapture(event.pointerId);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#the-gotpointercapture-event">Pointer Events – Level 2</a></td><td><span class="spec-rec">Recommendation</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#the-gotpointercapture-event">Pointer Events</a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

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

`gotpointercapture_event`

57

≤79

59

?

44

13

57

57

79

43

13

7.0

## See also

- Related events
  - [`lostpointercapture`](lostpointercapture_event)
  - [`pointerover`](pointerover_event)
  - [`pointerenter`](pointerenter_event)
  - [`pointerdown`](pointerdown_event)
  - [`pointermove`](pointermove_event)
  - [`pointerup`](pointerup_event)
  - [`pointercancel`](pointercancel_event)
  - [`pointerout`](pointerout_event)
  - [`pointerleave`](pointerleave_event)
- [`ongotpointercapture`](../globaleventhandlers/ongotpointercapture) event handler property
- This event on `HTMLElement` targets: [`gotpointercapture`](../htmlelement/gotpointercapture_event) event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/gotpointercapture_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/gotpointercapture_event</a>
