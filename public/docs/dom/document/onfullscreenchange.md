# Document.onfullscreenchange

The [`Document`](../document) interface's `onfullscreenchange` property is an event handler for the `fullscreenchange` event that is fired immediately before a document transitions into or out of full-screen mode.

## Syntax

    targetDocument.onfullscreenchange = fullscreenChangeHandler;

### Value

An event handler which is invoked whenever the document receives a `fullscreenchange` event, indicating that the document is transitioning into or out of full-screen mode.

## Usage notes

The `fullscreenchange` event does not directly specify whether the transition is into or out of full-screen mode, so your event handler should look at the value of [`Document.fullscreenElement`](fullscreenelement). If it's `null`, the event indicates a transition _out_ of full-screen mode. Otherwise, the specified element is about to take over the screen.

## Example

    document.onfullscreenchange = function ( event ) {
      console.log("FULL SCREEN CHANGE")
    };
    document.documentElement.onclick = function () {
      // requestFullscreen() must be in an event handler or it will fail
      document.documentElement.requestFullscreen();
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

45

12

64

10

11

Yes

5.1

71

45

71

45

64

10

Yes

5.1

5.0

## See also

- [Fullscreen API](../fullscreen_api)
- [Guide to the Fullscreen API](../fullscreen_api/guide)
- `fullscreenchange`
- [`Document.onfullscreenerror`](onfullscreenerror)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/onfullscreenchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/onfullscreenchange</a>
