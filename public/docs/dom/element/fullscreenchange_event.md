# Element: fullscreenchange event

The `fullscreenchange` event is fired immediately after an [`Element`](../element) switches into or out of full-screen mode.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="onfullscreenchange"><code>onfullscreenchange</code></a></td></tr></tbody></table>

This event is sent to the `Element` which is transitioning into or out of full-screen mode.

## Examples

In this example, a handler for the `fullscreenchange` event is added to the element whose ID is `fullscreen-div`.

If the user clicks on the "Toggle Fullscreen Mode" button, the `click` handler will toggle full-screen mode for the `div`. If `document.fullscreenElement` has a value it will exit full-screen mode. If not, the div will be placed into full-screen mode.

Remember that by the time the `fullscreenchange` event is handled, the status of the element has already changed. So if the change is to full-screen mode, `document.fullscreenElement` will point to the element that is now in full-screen mode. On the other hand, if `document.fullscreenElement` is null, full-screen mode has been canceled.

What that means to the example code is that, if an element is currently in full-screen mode, the `fullscreenchange` handler logs the `id` of the full-screen element to the console. If `document.fullscreenElement` is null, the code logs a message that the change is to leave full-screen mode.

### HTML

     <h1>fullscreenchange event example</h1>
     <div id="fullscreen-div">
       <button id="toggle-fullscreen">Toggle Fullscreen Mode</button>
     </div>

### JavaScript

    document.getElementById('fullscreen-div').addEventListener('fullscreenchange', (event) => {
      // document.fullscreenElement will point to the element that
      // is in fullscreen mode if there is one. If not, the value
      // of the property is null.
      if (document.fullscreenElement) {
        console.log(`Element: ${document.fullscreenElement.id} entered fullscreen mode.`);
      } else {
        console.log('Leaving full-screen mode.');
      }
    });

    document.getElementById('toggle-fullscreen').addEventListener('click', (event) => {
      if (document.fullscreenElement) {
        // exitFullscreen is only available on the Document object.
        document.exitFullscreen();
      } else {
        document.getElementById('fullscreen-div').requestFullscreen();
      }
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://fullscreen.spec.whatwg.org/">Fullscreen API</a></td><td><span class="spec-Living">Living Standard</span></td></tr></tbody></table>

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

57

???79

64

10

?

44

?

71

57

71

57

64

10

43

?

7.0

## See also

- [Document: fullscreenchange event](../document/fullscreenchange_event)
- [Element: fullscreenerror event](fullscreenerror_event)
- [Fullscreen API](../fullscreen_api)
- [Guide to the Fullscreen API](../fullscreen_api/guide)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/fullscreenchange_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/fullscreenchange_event</a>
