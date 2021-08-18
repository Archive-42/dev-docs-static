# HTMLMediaElement.currentTime

The [`HTMLMediaElement`](../htmlmediaelement) interface's `currentTime` property specifies the current playback time in seconds. Changing the value of `currentTime` seeks the media to the new time.

## Syntax

    var currentTime = htmlMediaElement.currentTime;
    htmlMediaElement.currentTime = 35;

### Value

A double-precision floating-point value indicating the current playback time in seconds.

If the media is not yet playing, the value of `currentTime` indicates the time position within the media at which playback will begin once the [`play()`](play) method is called.

Setting `currentTime` to a new value seeks the media to the given time, if the media is available.

For media without a known duration—such as media being streamed live—it's possible that the browser may not be able to obtain parts of the media that have expired from the media buffer. Also, media whose timeline doesn't begin at 0 seconds cannot be seeked to a time before its timeline's earliest time.

The length of the media in seconds can be determined using the [`duration`](duration) property.

## Example

    var video = document.createElement('video');
    console.log(video.currentTime);

## Usage notes

### Reduced time precision

To offer protection against timing attacks and fingerprinting, browsers may round or otherwise adjust the value returned by `currentTime`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#dom-media-currenttime">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.currentTime' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.currentTime' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`currentTime`

43

12

3.5

9

≤12.1

3.2

43

43

4

≤12.1

3

4.0

## See also

- The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).
- [`HTMLMediaElement.fastSeek()`](fastseek): Another way to set the time
- [`HTMLMediaElement.duration`](duration): The duration of the media in seconds

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/currentTime" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/currentTime</a>
