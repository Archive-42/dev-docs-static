# HTMLVideoElement.msIsLayoutOptimalForPlayback

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`msIsLayoutOptimalForPlayback` is a read-only property which indicates whether the video can be rendered more efficiently.

This proprietary property is specific to Internet Explorer and Microsoft Edge.

## Syntax

    HTMLVideoElement.msIsLayoutOptimalForPlayback: DOMString;

## Value

Boolean value set to _true_ indicates that video is being rendered optimally (better performance and using less battery power). If _false_, improvements can be made to optimize performance.

For `msIsLayoutOptimalForPlayback` to be true, avoid the following:

- Video elements with Cascading Style Sheets (CSS) outlines set.
- Rendering a video element through a canvas element.
- Embedding video elements in a Scalable Vector Graphics (SVG).

You can listen to the [onMSVideoOptimalLayoutChanged](onmsvideooptimallayoutchanged) event to be notified when the `msIsLayoutOptimalForPlayback` property changes.

\*To enable Stereo 3D playback, `msIsLayoutOptimalForPlayback` must be true.

## See also

- [`HTMLVideoElement`](../htmlvideoelement)
- [Microsoft API extensions](../microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/msIsLayoutOptimalForPlayback" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/msIsLayoutOptimalForPlayback</a>
