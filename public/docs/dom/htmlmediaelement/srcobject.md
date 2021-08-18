# HTMLMediaElement.srcObject

The `srcObject` property of the [`HTMLMediaElement`](../htmlmediaelement) interface sets or returns the object which serves as the source of the media associated with the [`HTMLMediaElement`](../htmlmediaelement). The object can be a [`MediaStream`](../mediastream), a [`MediaSource`](../mediasource), a [`Blob`](../blob), or a [`File`](../file) (which inherits from `Blob`).

**Note:** As of March 2020, only Safari supports setting objects other than `MediaStream`. Until other browsers catch up, for `MediaSource`, `Blob` and `File`, consider falling back to creating a URL with [`URL.createObjectURL()`](../url/createobjecturl) and assign it to [`HTMLMediaElement.src`](src). See below for an example.

## Syntax

    var sourceObject = HTMLMediaElement.srcObject;

    HTMLMediaElement.srcObject = sourceObject;

### Value

A [`MediaStream`](../mediastream), [`MediaSource`](../mediasource), [`Blob`](../blob), or [`File`](../file) object (though see the compatibility table for what is actually supported).

## Usage notes

Older versions of the Media Source specification required using [`createObjectURL()`](../url/createobjecturl) to create an object URL then setting [`src`](src) to that URL. Now you can just set `srcObject` to the [`MediaStream`](../mediastream) directly.

## Examples

### Basic example

In this example, a [`MediaStream`](../mediastream) from a camera is assigned to a newly-created [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element.

    const mediaStream = await navigator.mediaDevices.getUserMedia({video: true});
    const video = document.createElement('video');
    video.srcObject = mediaStream;

In this example, a new [`MediaSource`](../mediasource) is assigned to a newly-created [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element.

    const mediaSource = new MediaSource();
    const video = document.createElement('video');
    video.srcObject = mediaSource;

### Supporting fallback to the src property

The examples below support older browser versions that require you to create an object URL and assign it to `src` if `srcObject` isn't supported.

First, a [`MediaStream`](../mediastream) from a camera is assigned to a newly-created [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, with fallback for older browsers.

    const mediaStream = await navigator.mediaDevices.getUserMedia({video: true});
    const video = document.createElement('video');
    if ('srcObject' in video) {
      video.srcObject = mediaStream;
    } else {
      // Avoid using this in new browsers, as it is going away.
      video.src = URL.createObjectURL(mediaStream);
    }

Second, a new [`MediaSource`](../mediasource) is assigned to a newly-created [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element, with fallback for older browsers and browsers that don't yet support assignment of [`MediaSource`](../mediasource) directly.

    const mediaSource = new MediaSource();
    const video = document.createElement('video');
    // Older browsers may not have srcObject
    if ('srcObject' in video) {
      try {
        video.srcObject = mediaSource;
      } catch (err) {
        if (err.name != "TypeError") {
          throw err;
        }
        // Even if they do, they may only support MediaStream
        video.src = URL.createObjectURL(mediaSource);
      }
    } else {
      video.src = URL.createObjectURL(mediaSource);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#dom-media-srcobject">HTML Living Standard<br />
<span class="small">The definition of 'srcObject' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`srcObject`

52

Only supports `MediaStream` objects (see [bug 506273](https://crbug.com/506273)).

12

Only supports `MediaStream` objects (see [bug 506273](https://crbug.com/506273)).

42

Only supports `MediaStream` objects (see [bug 886194](https://bugzil.la/886194)).

18-58

No

39

Only supports `MediaStream` objects (see [bug 506273](https://crbug.com/506273)).

11

52

Only supports `MediaStream` objects (see [bug 506273](https://crbug.com/506273).

52

Only supports `MediaStream` objects (see [bug 506273](https://crbug.com/506273)).

42

Only supports `MediaStream` objects (see [bug 886194](https://bugzil.la/886194)).

18-58

41

Only supports `MediaStream` objects (see [bug 506273](https://crbug.com/506273)).

11

6.0

Only supports `MediaStream` objects (see [bug 506273](https://crbug.com/506273)).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/srcObject" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/srcObject</a>
