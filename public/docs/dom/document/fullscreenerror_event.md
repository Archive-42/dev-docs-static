# Document: fullscreenerror event

The `fullscreenerror` event is fired when the browser cannot switch to full-screen mode.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onfullscreenerror"><code>onfullscreenerror</code></a></td></tr></tbody></table>

As with the [`fullscreenchange` event](fullscreenchange_event), two `fullscreenerror` events are fired; the first is sent to the [`Element`](../element) which failed to change modes, and the second is sent to the [`Document`](../document) which owns that element.

For some reasons that switching into full-screen mode might fail, see [the guide to the Fullscreen API](../fullscreen_api/guide).

## Examples

    const requestor = document.querySelector('div');

    document.addEventListener('fullscreenerror', (event) => {
      console.error('an error occurred changing into fullscreen');
      console.log(event);
    });

    requestor.requestFullscreen();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://fullscreen.spec.whatwg.org/">Fullscreen API</a></td><td><span class="spec-living">Living Standard</span></td></tr></tbody></table>

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

`fullscreenerror_event`

71

45

12

64

10

11

32

?

71

45

71

45

64

10

32

?

5.0

## See also

- `fullscreenchange`
- [Fullscreen API](../fullscreen_api)
- [Guide to the Fullscreen API](../fullscreen_api/guide)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenerror_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenerror_event</a>
