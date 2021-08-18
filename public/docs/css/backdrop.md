# ::backdrop

The `::backdrop` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-element](pseudo-elements) is a box the size of the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport) which is rendered immediately beneath any element being presented in full-screen mode. This includes both elements which have been placed in full-screen mode using the [Fullscreen API](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API) and [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog) elements.

When multiple elements have been placed into full-screen mode, the backdrop is drawn immediately beneath the frontmost such element, and on top of the older full-screen elements.

    /* Backdrop is only displayed when dialog is opened with dialog.showModal() */
    dialog::backdrop {
      background: rgba(255,0,0,.25);
    }

All full-screen elements are placed in a last-in/first out (LIFO) stack in the top layer, which is a special layer in the viewport which is always rendered last (and therefore on top) before drawing the viewport's contents to the screen. The `::backdrop` pseudo-element makes it possible to obscure, style, or completely hide everything located below the element when it's the topmost one in the top layer.

`::backdrop` neither inherits from nor is inherited by any other elements. No restrictions are made on what properties apply to this pseudo-element.

## Syntax

    ::backdrop

## Examples

### Styling the backdrop for full-screen video

In this example, the backdrop style used when a video is shifted to full-screen mode is configured to be a grey-blue color rather than the black it defaults to in most browsers.

    video::backdrop {
      background-color: #448;
    }

The resulting screen looks like this:

<img src="https://developer.mozilla.org/en-US/docs/Web/CSS/::backdrop/bbb-backdrop.png" width="1000" height="563" />

[See this example in action](https://mdn.github.io/css-examples/backdrop/index.html), after changing the color of the background cause the video to go fullscreen to see the change to the backdrop color.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fullscreen.spec.whatwg.org/#::backdrop-pseudo-element">Fullscreen API<br />
<span class="small">The definition of '::backdrop' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`::backdrop`

37

32

12

47

11

24

19

No

37

≤37

37

32

47

24

19

No

3.0

2.0

`dialog`

32

79

No

No

19

No

≤37

32

No

19

No

2.0

`fullscreen`

No

12-79

47

11

No

No

No

No

47

No

No

No

## See also

- [`:fullscreen`](:fullscreen) pseudo-class
- [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog) HTML element
- [Fullscreen API](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/::backdrop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/::backdrop</a>
