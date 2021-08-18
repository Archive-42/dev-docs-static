# msIsBoxed

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`msIsBoxed` is a property which gets or sets when the video player control is in boxed (letterbox or pillarbox) mode.

This proprietary property is specific to Internet Explorer and Microsoft Edge.

Returns true if the video is in letterbox or pillarbox mode. Letterbox format displays black bars on the top and bottom of a video to fill in between the wide screen format of a video, and the aspect ratio of the screen. Typically the video's left and right edges go to the full width of the screen. Pillarbox format displays black bars on the left and right of a video to fill in the difference between a video and a wider screen. With pillarbox format, the top and bottom edges of the video go to the full height of the screen.

## Syntax

    isBoxed = object.msIsBoxed

## Value

Boolean value set to _true_ activates boxed mode for the video player.

Boolean value set to _false_ means the video player is zoomed to fill the screen.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MsIsBoxed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MsIsBoxed</a>
