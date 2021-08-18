# :picture-in-picture

The `:picture-in-picture` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) matches the element which is currently in picture-in-picture mode.

## Syntax

    :picture-in-picture

## Usage notes

The `:picture-in-picture` pseudo-class lets you configure your stylesheets to automatically adjust the size, style, or layout of content when a video switches back and forth between picture-in-picture and traditional presentation modes.

## Examples

In this example, a video has a box shadow when it is displayed in the floating window.

### HTML

The page's HTML looks like this:

    <h1>MDN Web Docs Demo: :picture-in-picture pseudo-class</h1>

    <p>This demo uses the <code>:picture-in-picture</code> pseudo-class to automatically
      change the style of a video entirely using CSS.</p>

    <video id="pip-video"></video>

The [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) with the ID `"pip-video"` will change between having a red box shadow or not, depending on whether or not it is displayed in the picture-in-picture floating window.

### CSS

The magic happens in the CSS.

    :picture-in-picture {
      box-shadow: 0 0 0 5px red;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/picture-in-picture/#:picture-in-picture-pseudo-class">Picture-in-Picture API<br />
<span class="small">The definition of ':picture-in-picture' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `css.selectors.picture-in-picture`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Picture-in-picture API](https://developer.mozilla.org/en-US/docs/Web/API/Picture-in-Picture_API)
- [`HTMLVideoElement.requestPictureInPicture()`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/requestPictureInPicture)
- [`HTMLVideoElement.autoPictureInPicture`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/autoPictureInPicture)
- [`HTMLVideoElement.disablePictureInPicture`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/disablePictureInPicture)
- [`Document.pictureInPictureEnabled`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pictureInPictureEnabled)
- [`Document.exitPictureInPicture()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/exitPictureInPicture)
- [`Document.pictureInPictureElement`](https://developer.mozilla.org/en-US/docs/Web/API/Document/pictureInPictureElement)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:picture-in-picture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:picture-in-picture</a>
