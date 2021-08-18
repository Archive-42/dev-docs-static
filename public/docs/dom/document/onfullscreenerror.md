# Document.onfullscreenerror

The `Document.onfullscreenerror` property is an event handler for the `fullscreenerror` event that is sent to the document when it fails to transition into full-screen mode after a prior call to [`Element.requestFullscreen()`](../element/requestfullscreen).

## Syntax

    targetDocument.onfullscreenerror = fullscreenErrorHandler;

### Value

An event handler for the `fullscreenerror` event.

## Example

This example attempts to call `requestFullscreen()` outside of an event handler. Since `requestFullscreen()` can only be called in response to user action, for security reasons, this will fail, causing the `fullscreenerror` to be sent to the document.

    document.onfullscreenerror = function ( event ) {
      displayWarning("Unable to switch into full-screen mode.");
    };

    //....

    document.documentElement.requestFullscreen();

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

45

12

64

10

11

Yes

6

71

45

71

45

64

10

Yes

6

5.0

## See also

- [Fullscreen API](../fullscreen_api)
- [Guide to the Fullscreen API](../fullscreen_api/guide)
- `fullscreenerror`
- [`Document.onfullscreenchange`](onfullscreenchange)
- [`Element.onfullscreenerror`](../element/onfullscreenerror)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/onfullscreenerror" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/onfullscreenerror</a>
