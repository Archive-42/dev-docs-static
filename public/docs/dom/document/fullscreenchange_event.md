# Document: fullscreenchange event

The `fullscreenchange` event is fired immediately after the browser switches into or out of full-screen mode.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onfullscreenchange"><code>onfullscreenchange</code></a></td></tr></tbody></table>

The event is sent to the `Element` that is transitioning into or out of full-screen mode, and this event then bubbles up to the `Document`.

To find out whether the `Element` is entering or exiting full-screen mode, check the value of [`Document.fullscreenElement`](fullscreenelement): if this value is `null` then the element is exiting full-screen mode, otherwise it is entering full-screen mode.

## Examples

In this example, a handler for the `fullscreenchange` event is added to the [`Document`](../document).

    document.addEventListener('fullscreenchange', (event) => {
      // document.fullscreenElement will point to the element that
      // is in fullscreen mode if there is one. If there isn't one,
      // the value of the property is null.
      if (document.fullscreenElement) {
        console.log(`Element: ${document.fullscreenElement.id} entered full-screen mode.`);
      } else {
        console.log('Leaving full-screen mode.');
      }
    });

See [Element: fullscreenchange event](../element/fullscreenchange_event) for another example.

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

`fullscreenchange_event`

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

- [`fullscreenerror`](fullscreenerror_event)
- [`Element`](../element): [`fullscreenchange`](../element/fullscreenchange_event) event
- [Fullscreen API](../fullscreen_api)
- [Guide to the Fullscreen API](../fullscreen_api/guide)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenchange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenchange_event</a>
