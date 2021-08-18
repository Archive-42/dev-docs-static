# Audio()

The `Audio()` constructor creates and returns a new [`HTMLAudioElement`](../htmlaudioelement) which can be either attached to a document for the user to interact with and/or listen to, or can be used offscreen to manage and play audio.

## Syntax

    audioObj = new Audio(url);

### Parameters

`url` <span class="badge inline optional">Optional</span>  
An optional [`DOMString`](../domstring) containing the URL of an audio file to be associated with the new audio element.

### Return value

A new [`HTMLAudioElement`](../htmlaudioelement) object, configured to be used for playing back the audio from the file specified by `url`.The new object's <span class="page-not-created">`preload`</span> property is set to `auto` and its `src` property is set to the specified URL or `null` if no URL is given. If a URL is specified, the browser begins to _asynchronously_ load the media resource before returning the new object.

## Usage notes

You can also use other element-creation methods, such as the [`document`](../document) object's [`createElement()`](../document/createelement) method, to construct a new [`HTMLAudioElement`](../htmlaudioelement).

### Determining when playback can begin

There are three ways you can tell when enough of the audio file has loaded to allow playback to begin:

- Check the value of the [`readyState`](../htmlmediaelement/readystate) property. If it's `HTMLMediaElement.HAVE_FUTURE_DATA`, there's enough data available to begin playback and play for at least a short time. If it's `HTMLMediaElement.HAVE_ENOUGH_DATA`, then there's enough data available that, given the current download rate, you should be able to play the audio through to the end without interruption.
- Listen for the [`canplay`](../htmlmediaelement/canplay_event) event. It is sent to the `<audio>` element when there's enough audio available to begin playback, although interruptions may occur).
- Listen for the [`canplaythrough`](../htmlmediaelement/canplaythrough_event) event. It is sent when it's estimated that the audio should be able to play to the end without interruption.

The event-based approach is best:

    myAudioElement.addEventListener("canplaythrough", event => {
      /* the audio is now playable; play it if permissions allow */
      myAudioElement.play();
    });

### Memory usage and management

If all references to an audio element created using the `Audio()` constructor are deleted, the element itself won't be removed from memory by the JavaScript runtime's garbage collection mechanism if playback is currently underway. Instead, the audio will keep playing and the object will remain in memory until playback ends or is paused (such as by calling [`pause()`](../htmlmediaelement/pause)). At that time, the object becomes subject to garbage collection.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-audio">HTML Living Standard<br />
<span class="small">The definition of 'Audio()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`Audio`

3

12

3.5

9

≤12.1

3.1

≤37

18

4

≤12.1

2

1.0

The compatibility table on this page is generated from structured data. If you'd like to contribute to the data, please check out <https://github.com/mdn/browser-compat-data> and send us a pull request.

## See also

- [Web media technologies](https://developer.mozilla.org/en-US/docs/Web/Media)
- HTML element implementing this interface: [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAudioElement/Audio" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAudioElement/Audio</a>
