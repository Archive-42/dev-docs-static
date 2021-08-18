# Element.onfullscreenchange

The [`Element`](../element) interface's `onfullscreenchange` property is an event handler for the `fullscreenchange` event that is fired when the element has transitioned into or out of full-screen mode.

## Syntax

    targetDocument.onfullscreenchange = fullscreenChangeHandler;

### Value

An event handler for the `fullscreenchange` event, indicating that the element has changed in or out of full-screen mode.

## Example

This example establishes a `fullscreenchange` event handler, `handleFullscreenChange()`. This function determines which element it was called on by checking the value of [`event.target`](../event/target), then compares the document's [`fullscreenElement`](../document/fullscreenelement) value to the element to see if they're the same node.

This gives us a value, `isFullscreen`, which we pass into a function called `adjustMyControls()`, which we imagine to be a function that makes adjustments to the app's user interface to present itself optimally when it's in full-screen mode versus being displayed in a window.

    function toggleFullscreen() {
      let elem = document.querySelector("video");

      elem.onfullscreenchange = handleFullscreenChange;
      if (!document.fullscreenElement) {
        elem.requestFullscreen().then({}).catch(err => {
          alert(`Error attempting to enable full-screen mode: ${err.message} (${err.name})`);
        });
      } else {
        document.exitFullscreen();
      }
    }

    function handleFullscreenChange(event) {
      let elem = event.target;
      let isFullscreen = document.fullscreenElement === elem;

      adjustMyControls(isFullscreen);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fullscreen.spec.whatwg.org/#handler-document-onfullscreenchange">Fullscreen API<br />
<span class="small">The definition of 'onfullscreenchange' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onfullscreenchange`

71

57

79

64

10

No

Yes

No

71

57

71

57

64

10

Yes

No

7.0

## See also

- [Fullscreen API](../fullscreen_api)
- [Guide to the Fullscreen API](../fullscreen_api/guide)
- `fullscreenchange`
- [`Element.onfullscreenerror`](onfullscreenerror)
- The [`Document`](../document) equivalent: [`onfullscreenchange`](../document/onfullscreenchange).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/onfullscreenchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/onfullscreenchange</a>
