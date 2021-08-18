# HTMLElement: pointermove event

The `pointermove` event is fired when a pointer changes coordinates, and the pointer has not been [canceled](pointercancel_event) by a browser [touch-action](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action).

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../pointerevent"><code>PointerEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onpointermove"><code>onpointermove</code></a></td></tr></tbody></table>

## Usage notes

The event, which is of type [`PointerEvent`](../pointerevent), provides all the information you need to know about the user's interaction with the pointing device, including the position, movement distance, button states, and much more.

## Examples

To add a handler for `pointermove` events using [`addEventListener()`](../eventtarget/addeventlistener):

    const para = document.querySelector('p');

    para.addEventListener('pointermove', (event) => {
      console.log('Pointer moved');
    });

You can also use the `onpointermove` event handler property:

    const para = document.querySelector('p');

    para.onpointermove = (event) => {
      console.log('Pointer moved');
    };

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>comments</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#the-pointermove-event">Pointer Events – Level 2</a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#the-pointermove-event">Pointer Events</a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

- `gotpointercapture`
- `lostpointercapture`
- `pointerover`
- `pointerenter`
- `pointerdown`
- `pointerup`
- `pointercancel`
- `pointerout`
- `pointerleave`
- `onpointermove` event handler property
- This event on `Document` targets: `pointermove` event

Internet Explorer also used to support an event named `MSPointerHover`, which fired when a contact (normally a pen) moves over an element without touching the surface. This proprietary method is specific to Internet Explorer and, as of Internet Explorer 11, has been deprecated. Starting with IE11 the `pointermove` event will fire for all pen movement (regardless if its hovering or not).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointermove_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointermove_event</a>
