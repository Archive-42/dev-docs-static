# HTMLAudioElement

The `HTMLAudioElement` interface provides access to the properties of [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) elements, as well as methods to manipulate them. It's based on, and inherits properties and methods from, the [`HTMLMediaElement`](htmlmediaelement) interface.

## Constructor

[`Audio()`](htmlaudioelement/audio)  
Creates and returns a new `HTMLAudioElement` object, optionally starting the process of loading an audio file into it if the file URL is given.

## Properties

_No specific properties; inherits properties from its parent, [`HTMLMediaElement`](htmlmediaelement), and from [`HTMLElement`](htmlelement)._

## Methods

_Inherits methods from its parent, [`HTMLMediaElement`](htmlmediaelement), and from [`HTMLElement`](htmlelement). It offers no methods of its own._

### Obsolete Mozilla-only methods

_The following methods are non-standard and should not be used._

<span class="page-not-created">`mozCurrentSampleOffset()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns the number of samples form the beginning of the stream that have been written so far into the audio stream created by calling <span class="page-not-created">`mozWriteAudio()`</span>.

<span class="page-not-created">`mozSetup()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Sets up the audio stream to allow writing, given the number of audio channels (1 or 2) and the sample rate in kHz.

<span class="page-not-created">`mozWriteAudio()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Writes a batch of audio frames to the stream at the current offset, returning the number of bytes actually written to the stream.

## Examples

### Basic usage

You can create a `HTMLAudioElement` entirely with JavaScript using the [`Audio()`](htmlaudioelement/audio) constructor:

    var audioElement = new Audio('car_horn.wav');

then you can invoke the `play()` method on the element

    audioElement.play();

A common gotcha is trying to play an audio element immediately on page load. Modern browser's default autoplay policy will block that from happening. Refer to [firefox](https://hacks.mozilla.org/2019/02/firefox-66-to-block-automatically-playing-audible-video-and-audio/) and [chrome](https://developers.google.com/web/updates/2017/09/autoplay-policy-changes) for best practices and work arounds.

Some of the more commonly used properties of the audio element include [`src`](htmlmediaelement/src), [`currentTime`](htmlmediaelement/currenttime), [`duration`](htmlmediaelement/duration), [`paused`](htmlmediaelement/paused), [`muted`](htmlmediaelement/muted), and [`volume`](htmlmediaelement/volume). This snippet copies the audio file's duration to a variable:

    var audioElement = new Audio('car_horn.wav');
    audioElement.addEventListener('loadeddata', () => {
      let duration = audioElement.duration;
      // The duration variable now holds the duration (in seconds) of the audio clip
    })

## Events

_Inherits methods from its parent, [`HTMLMediaElement`](htmlmediaelement), and from its ancestor [`HTMLElement`](htmlelement)._ Listen to events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlaudioelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLAudioElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#the-audio-element">HTML5<br />
<span class="small">The definition of 'HTMLAudioElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`HTMLAudioElement`

1

12

3.5

9

10.5

3.1

1

18

4

11

2

1.0

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

`mozCurrentSampleOffset`

No

No

4-28

No

No

No

No

No

4-28

No

No

No

`mozSetup`

No

No

4-28

No

No

No

No

No

4-28

No

No

No

`mozWriteAudio`

No

No

4-28

No

No

No

No

No

4-28

No

No

No

## See also

- [Web media technologies](https://developer.mozilla.org/en-US/docs/Web/Media)
- [Using audio and video in HTML](https://developer.mozilla.org/en-US/docs/Web/Media/HTML_media)
- HTML element implementing this interface: [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLAudioElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLAudioElement</a>
