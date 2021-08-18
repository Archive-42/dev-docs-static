# HTMLElement: lostpointercapture event

The `lostpointercapture` event is fired when a [captured pointer](../pointer_events#pointer_capture) is released.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../pointerevent"><code>PointerEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onlostpointercapture</code></td></tr></tbody></table>

## Examples

This example listens for the `lostpointercapture` event for an element, and captures the pointer for the element on `pointerdown`. When the user subsequently releases the pointer, the `lostpointercapture` event will be fired.

    const para = document.querySelector('p');

    para.addEventListener('lostpointercapture', () => {
      console.log('I\'ve been released!')
    });

    para.addEventListener('pointerdown', (event) => {
      para.setPointerCapture(event.pointerId);
    });

The same example, but using the `onlostpointercapture` event handler property:

    const para = document.querySelector('p');

    para.onlostpointercapture = () => {
      console.log('I\'ve been released!')
    };

    para.addEventListener('pointerdown', (event) => {
      para.setPointerCapture(event.pointerId);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#the-lostpointercapture-event">Pointer Events – Level 2</a></td><td><span class="spec-rec">Recommendation</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#the-lostpointercapture-event">Pointer Events</a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

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

`lostpointercapture_event`

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
  - `gotpointercapture`
  - `pointerover`
  - `pointerenter`
  - `pointerdown`
  - `pointermove`
  - `pointerup`
  - `pointercancel`
  - `pointerout`
  - `pointerleave`
- `onlostpointercapture` event handler property
- This event on `Document` targets: `lostpointercapture` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/lostpointercapture_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/lostpointercapture_event</a>
