# HTMLMediaElement.seekToNextFrame()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `HTMLMediaElement.seekToNextFrame()` method asynchronously advances the current play position to the next frame in the media.

This non-standard method is part of an experimentation process around support for non-real-time access to media for tasks including filtering, editing, and so forth. You should _not_ use this method in production code, because its implementation may change—or be removed outright—without notice. You are, however, invited to experiment with it.

This method lets you access frames of video media without the media being performed in real time. This also lets you access media using frames as a seek unit rather than timecodes (albeit only by seeking one frame at a time until you get to the frame you want). Possible uses for this method include filtering and editing of video content.

This method returns immediately, returning a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise), whose fulfillment handler is called when the seek operation is complete. In addition, a `seeked` event is sent to let interested parties know that a seek has taken place. If the seek fails because the media is already at the last frame, a `seeked` event occurs, followed immediately by an `ended` event.

If there is no video on the media element, or the media isn't seekable, nothing happens.

## Syntax

    var seekCompletePromise = HTMLMediaElement.seekToNextFrame();

    HTMLMediaElement.seekToNextFrame();

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is fulfilled once the seek operation has completed.

Firefox 49 returns [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined) instead of a promise, and performs the seek operation synchronously.

## Specifications

Not part of any specification.

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

`seekToNextFrame`

No

No

56

No

?

No

No

?

56

?

No

?

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/seekToNextFrame" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/seekToNextFrame</a>
