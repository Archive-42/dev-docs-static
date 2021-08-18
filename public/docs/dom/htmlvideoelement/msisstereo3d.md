# HTMLVideoElement.msIsStereo3D

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`msIsStereo3D` is a read-only property which determines whether the system considers the loaded video source to be stereo 3-D or not.

This proprietary property is specific to Internet Explorer and Microsoft Edge.

## Syntax

    HTMLVideoElement.msIsStereo3D: boolean;

## Value

[`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value set to _true_ indicates that the video source is stereo 3D.

This uses metadata set in MP4 or MPEG-2 file containers and H.264 Supplemental enhancement information (SEI) messages to determine the stereo capability of the source.

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

`msIsStereo3D`

No

12-79

No

10

No

No

No

No

No

No

No

No

## See also

- [`HTMLVideoElement`](../htmlvideoelement)
- [Microsoft API extensions](../microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/msIsStereo3D" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLVideoElement/msIsStereo3D</a>
