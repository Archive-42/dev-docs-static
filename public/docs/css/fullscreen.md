# :fullscreen

The `:fullscreen` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) matches every element which is currently in full-screen mode. If multiple elements have been put into full-screen mode, this selects them all.

## Syntax

    :fullscreen

## Usage notes

The `:fullscreen` pseudo-class lets you configure your stylesheets to automatically adjust the size, style, or layout of content when elements switch back and forth between full-screen and traditional presentations.

## Examples

In this example, the color of a button is changed depending on whether or not the document is in full-screen mode. This is done without needing to specifically apply style changes using JavaScript.

### HTML

The page's HTML looks like this:

    <h1>MDN Web Docs Demo: :fullscreen pseudo-class</h1>

    <p>This demo uses the <code>:fullscreen</code> pseudo-class to automatically
      change the style of a button used to toggle full-screen mode on and off,
      entirely using CSS.</p>

    <button id="fs-toggle">Toggle Fullscreen</button>

The [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) with the ID `"fs-toggle"` will change between pale red and pale green depending on whether or not the document is in full-screen mode.

### CSS

The magic happens in the CSS. There are two rules here. The first establishes the background color of the "Toggle Full-screen Mode" button when the element is not in a full-screen state. The key is the use of the `:not(:fullscreen)`, which looks for the element to not have the `:fullscreen` pseudo-class applied to it.

    #fs-toggle:not(:fullscreen) {
      background-color: #afa;
    }

When the document _is_ in full-screen mode, the following CSS applies instead, setting the background color to a pale shade of red.

    #fs-toggle:fullscreen {
      background-color: #faa;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://fullscreen.spec.whatwg.org/#:fullscreen-pseudo-class">Fullscreen API<br />
<span class="small">The definition of ':fullscreen' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:fullscreen`

71

15

12

64

9

11

58

15

6

71

37

71

18

64

9

50

14

No

10.0

1.0

`all_elements`

No

12-79

43

11

No

No

No

No

43

No

No

No

## See also

- [Fullscreen API](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API)
- [Guide to the Fullscreen API](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API/Guide)
- [`:not`](:not)
- [`::backdrop`](::backdrop)
- DOM API: [`Element.requestFullscreen()`](https://developer.mozilla.org/en-US/docs/Web/API/Element/requestFullScreen), [`Document.exitFullscreen()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/exitFullscreen), [`Document.fullscreenElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/fullscreenElement)
- [`allowfullscreen`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-allowfullscreen) attribute

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:fullscreen" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:fullscreen</a>
