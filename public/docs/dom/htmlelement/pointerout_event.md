HTMLElement: pointerout event
=============================

The `pointerout` event is fired for several reasons including: pointing device is moved out of the *hit test* boundaries of an element; firing the `pointerup` event for a device that does not support hover (see `pointerup`); after firing the `pointercancel` event (see `pointercancel`); when a pen stylus leaves the hover range detectable by the digitizer.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../pointerevent"><code>PointerEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onpointerout</code></td></tr></tbody></table>

Examples
--------

Using `addEventListener()`:

    const para = document.querySelector('p');

    para.addEventListener('pointerout', (event) => {
      console.log('Pointer moved out');
    });

Using the `onpointerout` event handler property:

    const para = document.querySelector('p');

    para.onpointerout = (event) => {
      console.log('Pointer moved out');
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#the-pointerout-event">Pointer Events – Level 2</a></td><td><span class="spec-rec">Recommendation</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#the-pointerout-event">Pointer Events</a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

Browser compatibility
---------------------

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

`pointerout_event`

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

See also
--------

-   `gotpointercapture`
-   `lostpointercapture`
-   `pointerover`
-   `pointerenter`
-   `pointerdown`
-   `pointermove`
-   `pointerup`
-   `pointercancel`
-   `pointerleave`
-   `onpointerout` event handler property
-   This event on `Document` targets: `pointerout` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerout_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerout_event</a>
