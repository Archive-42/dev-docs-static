# Element.onfullscreenerror

The [`Element`](../element) interface's `onfullscreenerror` property is an event handler for the [`fullscreenerror`](fullscreenerror_event) event which is sent to the element when an error occurs while attempting to transition into or out of full-screen mode.

## Syntax

    targetElement.onfullscreenerror = fullscreenErrorHandler;

### Value

An error handler for the [`fullscreenerror`](fullscreenerror_event) event.

## Example

This example attempts to switch into full-screen mode from outside a handler for a user-initiated event (such as a [`click`](click_event) or [`keypress`](keypress_event) event). Since full-screen mode changes are only permitted in response to a user input, this causes an error to occur, which triggers the delivery of the [`fullscreenerror`](fullscreenerror_event) event to the error handler,

    let elem = document.querySelector("video")}}

    elem.onfullscreenerror = function ( event ) {
      displayWarning("Unable to switch into full-screen mode.");
    };

    //....

    elem.requestFullscreen();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fullscreen.spec.whatwg.org/#handler-document-onfullscreenerror">Fullscreen API<br />
<span class="small">The definition of 'onfullscreenerror' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onfullscreenerror`

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
- [`fullscreenerror`](fullscreenerror_event)
- [`Element.onfullscreenerror`](onfullscreenerror)
- [`Document.onfullscreenerror`](../document/onfullscreenerror)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/onfullscreenerror" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/onfullscreenerror</a>
