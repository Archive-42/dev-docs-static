# Document.fullscreenEnabled

The read-only `fullscreenEnabled` property on the [`Document`](../document) interface indicates whether or not full-screen mode is available. Full-screen mode is available only for a page that has no windowed plug-ins in any of its documents, and if all [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) elements which contain the document have their [`allowfullscreen`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-allowfullscreen) attribute set.

Although this property is read-only, it will not throw if it is modified (even in strict mode); the setter is a no-operation and it will be ignored.

## Syntax

    var isFullscreenAvailable = document.fullscreenEnabled;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value which is `true` if the document and the elements within can be placed into full-screen mode by calling [`Element.requestFullscreen()`](../element/requestfullscreen). If full-screen mode isn't available, this value is `false`.

## Example

In this example, before attempting to request full-screen mode for a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, the value of `fullscreenEnabled` is checked, in order to avoid making the attempt when not available.

    function requestFullScreen() {
      if (document.fullscreenEnabled) {
        videoElement.requestFullScreen();
      } else {
        console.log('Your browser cannot use fullscreen right now');
      }
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fullscreen.spec.whatwg.org/#dom-document-fullscreenenabled">Fullscreen API<br />
<span class="small">The definition of 'Document.fullscreenEnabled' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`fullscreenEnabled`

71

Yes

12

64

10

11

Yes

6

71

Yes

71

Yes

64

10

Yes

6

10.0

Yes

## See also

- [Fullscreen API](../fullscreen_api)
- [Guide to the Fullscreen API](../fullscreen_api/guide)
- [`Element.requestFullscreen()`](../element/requestfullscreen)
- [`Document.exitFullscreen()`](exitfullscreen)
- [`Document.fullscreenElement`](fullscreenelement)
- [`:fullscreen`](https://developer.mozilla.org/en-US/docs/Web/CSS/:fullscreen) and [`::backdrop`](https://developer.mozilla.org/en-US/docs/Web/CSS/::backdrop)
- The [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) [`allowfullscreen`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-allowfullscreen) attribute

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenEnabled" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenEnabled</a>
