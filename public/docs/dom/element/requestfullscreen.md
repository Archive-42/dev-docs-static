# Element.requestFullscreen()

The `Element.requestFullscreen()` method issues an asynchronous request to make the element be displayed in full-screen mode.

It's not guaranteed that the element will be put into full screen mode. If permission to enter full screen mode is granted, the returned [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) will resolve and the element will receive a `fullscreenchange` event to let it know that it's now in full screen mode. If permission is denied, the promise is rejected and the element receives a `fullscreenerror` event instead. If the element has been detached from the original document, then the document receives these events instead.

Earlier implementations of the Fullscreen API would always send these events to the document rather than the element, and you may need to be able to handle that situation. Check [Browser compatibility](https://developer.mozilla.org/en-US/docs/Web/Events/fullscreen#Browser_compatibility) in [\[Page not yet written\]](https://developer.mozilla.org/en-US/docs/Web/Events/fullscreen) for specifics on when each browser made this change.

**Note:** This method must be called while responding to a user interaction or a device orientation change; otherwise it will fail.

## Syntax

    var promise = element.requestFullscreen(options);

### Parameters

`options` <span class="badge inline optional">Optional</span>  
A [`FullscreenOptions`](../fullscreenoptions) object providing options that control the behavior of the transition to full-screen mode. Currently, the only option is [`navigationUI`](../fullscreenoptions/navigationui), which controls whether or not to show navigation UI while the element is in full-screen mode. The default value is `"auto"`, which indicates that the browser should decide what to do.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is resolved with a value of `undefined` when the transition to full screen is complete.

### Exceptions

_Rather than throw a traditional exception, the `requestFullscreen()` procedure announces error conditions by rejecting the `Promise` it has returned. The rejection handler receives one of the following exception values:_

[`TypeError`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypeError)  
The `TypeError` exception may be delivered in any of the following situations:

- The document containing the element isn't fully active; that is, it's not the current active document.
- The element is not contained by a document.
- The element is not permitted to use the `"fullscreen"` feature, either because of Feature Policy configuration or other access control features.
- The element and its document are the same node.

## Usage notes

### Compatible elements

An element that you wish to place into full-screen mode has to meet a small number of simple requirements:

- It must be one of the standard HTML elements or [`<svg>`](https://developer.mozilla.org/en-US/docs/Web/SVG/Element/svg) or `<math>`.
- It is _not_ a [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog) element.
- It must either be located within the top-level document or in an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) which has the [`allowfullscreen`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-allowfullscreen) attribute applied to it.

Additionally, of course, the Feature Policy `"fullscreen"` permission must be granted.

### Detecting full-screen activation

You can determine whether or not your attempt to switch to full-screen mode is successful by using the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by `requestFullscreen()`, as seen in the [Example](#example) below.

To learn when other code has toggled full-screen mode on and off, you should establish listeners for the `fullscreenchange` event on the [`Document`](../document). It's also important to listen for `fullscreenchange` to be aware when, for example, the user manually toggles full-screen mode, or when the user switches applications, causing your application to temporarily exit full-screen mode.

## Examples

This function toggles the first [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element found in the document into and out of full-screen mode.

    function toggleFullscreen() {
      let elem = document.querySelector("video");

      if (!document.fullscreenElement) {
        elem.requestFullscreen().catch(err => {
          alert(`Error attempting to enable full-screen mode: ${err.message} (${err.name})`);
        });
      } else {
        document.exitFullscreen();
      }
    }

If the document isn't already in full-screen mode—detected by looking to see if [`document.fullscreenElement`](../document/fullscreenelement) has a value—we call the video's `requestFullscreen()` method. We don't need to do anything special if successful, but if the request fails, our promise's `catch()` handler presents an alert with an appropriate error message.

If, on the other hand, full-screen mode is already in effect, we call [`document.exitFullscreen()`](../document/exitfullscreen) to disable full-screen mode.

You can [see this example in action](https://fullscreen-requestfullscreen-demo.glitch.me/) or [view or remix the code](https://glitch.com/edit/#!/fullscreen-requestfullscreen-demo) on [Glitch](https://glitch.com/).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fullscreen.spec.whatwg.org/#dom-element-requestfullscreen">Fullscreen API<br />
<span class="small">The definition of 'Element.requestFullscreen()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`requestFullScreen`

71

15

79

79

12-14

64

9

Before Firefox 44, Firefox incorrectly allowed elements inside a `<frame>` or `<object>` element to request, and to be granted, fullscreen. In Firefox 44 and onwards this has been fixed: only elements in the top-level document or in an `<iframe>` element with the `allowfullscreen` attribute can be displayed fullscreen.

11

58

15

12-15

6

71

≤37

71

18

64

9

Before Firefox 44, Firefox incorrectly allowed elements inside a `<frame>` or an `<object>` to request, and to be granted, fullscreen. In Firefox 44 and onwards this has been fixed: only elements in the top-level document or in an `<iframe>` with the `allowfullscreen` attribute can be displayed fullscreen.

50

14

12-14

6

Only available on iPad, not on iPhone. Shows an overlay button which can not be disabled.

10.0

1.0

`options_parameter`

71

79

64

No

?

?

71

71

64

?

?

10.0

`returns_a_promise`

69

79

64

No

No

No

69

69

64

No

No

10.0

## See also

- [Fullscreen API](../fullscreen_api)
- [`Document.exitFullscreen()`](../document/exitfullscreen)
- [`Document.fullscreen`](../document/fullscreen)
- [`Document.fullscreenElement`](../document/fullscreenelement)
- [`:fullscreen`](https://developer.mozilla.org/en-US/docs/Web/CSS/:fullscreen)
- [`allowfullscreen`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-allowfullscreen)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/requestFullScreen" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/requestFullScreen</a>
