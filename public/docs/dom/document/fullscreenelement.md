# Document.fullscreenElement

The `Document.fullscreenElement` read-only property returns the [`Element`](../element) that is currently being presented in full-screen mode in this document, or `null` if full-screen mode is not currently in use.

Although this property is read-only, it will not throw if it is modified (even in strict mode); the setter is a no-operation and it will be ignored.

## Syntax

    document.fullscreenElement

### Return value

The [`Element`](../element) object that's currently in full-screen mode; if full-screen mode isn't currently in use by the `document`&gt;, the returned value is `null`.

## Example

This example presents a function, `isVideoInFullscreen()`, which looks at the value returned by `fullscreenElement`; if the document is in full-screen mode (`fullscreenElement` isn't `null`) and the full-screen element's [`nodeName`](../node/nodename) is `VIDEO`, indicating a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, the function returns `true`, indicating that the video is in full-screen mode.

    function isVideoInFullscreen() {
      if (document.fullscreenElement && document.fullscreenElement.nodeName == 'VIDEO') {
        return true;
      }
      return false;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://fullscreen.spec.whatwg.org/#dom-document-fullscreenelement">Fullscreen API<br />
<span class="small">The definition of 'Document.fullscreenElement' in that specification.</span></a></td></tr></tbody></table>

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

`fullscreenElement`

71

53

≤79

≤18

12

64

9

Yes

58

40

Yes

71

53

71

53

64

9

50

41

12

Full-screen mode is only supported on the iPad.

10.0

6.0

## See also

- [Fullscreen API](../fullscreen_api)
- [Guide to the Fullscreen API](../fullscreen_api/guide)
- [`Element.requestFullscreen()`](../element/requestfullscreen)
- [`Document.exitFullscreen()`](exitfullscreen)
- [`:fullscreen`](https://developer.mozilla.org/en-US/docs/Web/CSS/:fullscreen) and [`::backdrop`](https://developer.mozilla.org/en-US/docs/Web/CSS/::backdrop)
- The [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) [`allowfullscreen`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-allowfullscreen) attribute

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenElement</a>
