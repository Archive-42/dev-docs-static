# Document.exitFullscreen()

The [`Document`](../document) method `exitFullscreen()` requests that the element on this document which is currently being presented in full-screen mode be taken out of full-screen mode, restoring the previous state of the screen. This usually reverses the effects of a previous call to [`Element.requestFullscreen()`](../element/requestfullscreen).

## Syntax

    exitPromise = document.exitFullscreen();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is resolved once the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) has finished exiting full-screen mode. If an error occurs while attempting to exit full-screen mode, the `catch()` handler for the promise is called.

## Example

This example causes the current document to toggle in and out of a full-screen presentation whenever the mouse button is clicked within it.

    document.onclick = function (event) {
      if (document.fullscreenElement) {
        document.exitFullscreen()
          .then(() => console.log("Document Exited from Full screen mode"))
          .catch((err) => console.error(err))
      } else {
        document.documentElement.requestFullscreen();
      }
    }

**Note:** For a more complete example, see the [Example](../element/requestfullscreen#example) in [Element.requestFullscreen()](../element/requestfullscreen).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fullscreen.spec.whatwg.org/#dom-document-exitfullscreen">Fullscreen API<br />
<span class="small">The definition of 'Document.exitFullscreen()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`exitFullscreen`

71

15

12

64

9

11

15

5.1

71

≤37

71

18

64

9

Yes

No

10.0

1.0

`returns_a_promise`

69

79

64

No

?

?

69

69

64

?

No

10.0

## See also

- [Fullscreen API](../fullscreen_api)
- [Guide to the Fullscreen API](../fullscreen_api/guide)
- [`Element.requestFullscreen()`](../element/requestfullscreen)
- [`Document.fullscreenElement`](fullscreenelement)
- [`:fullscreen`](https://developer.mozilla.org/en-US/docs/Web/CSS/:fullscreen) and [`::backdrop`](https://developer.mozilla.org/en-US/docs/Web/CSS/::backdrop)
- The [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) [`allowfullscreen`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-allowfullscreen) attribute

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/exitFullscreen" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/exitFullscreen</a>
