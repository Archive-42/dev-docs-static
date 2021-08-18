# HTMLMediaElement.load()

The [`HTMLMediaElement`](../htmlmediaelement) method `load()` resets the media element to its initial state and begins the process of selecting a media source and loading the media in preparation for playback to begin at the beginning. The amount of media data that is prefetched is determined by the value of the element's [`preload`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-preload) attribute.

This method is generally only useful when you've made dynamic changes to the set of sources available for the media element, either by changing the element's [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-src) attribute or by adding or removing [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source) elements nested within the media element itself. `load()` will reset the element and rescan the available sources, thereby causing the changes to take effect.

## Syntax

    mediaElement.load();

### Parameters

None.

### Return value

`undefined`.

## Usage notes

Calling `load()` aborts all ongoing operations involving this media element, then begins the process of selecting and loading an appropriate media resource given the options specified in the [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element and its [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-src) attribute or child [`<source>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/source) element(s). This is described in more detail in [Supporting multiple formats](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content#supporting_multiple_formats) in [Video and audio content](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content).

The process of aborting any ongoing activities will cause any outstanding [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise)s returned by [`play()`](play) being resolved or rejected as appropriate based on their status before the loading of new media can begin. Pending play promises are aborted with an `"AbortError"` [`DOMException`](../domexception).

Appropriate events will be sent to the media element itself as the load process proceeds:

- If the element is already in the process of loading media, that load process is aborted and the `abort` event is sent.
- If the element has already been initialized with media, the `emptied` event is sent.
- If resetting the playback position to the beginning of the media actually changes the playback position (that is, it was not already at the beginning), a `timeupdate` event is sent.
- Once media has been selected and loading is ready to begin, the `loadstart` event is delivered.
- From this point onward, events are sent just like any media load.

## Example

This example finds a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element in the document and resets it by calling `load()`.

    var mediaElem = document.querySelector("video");
    mediaElem.load();

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/media.html#dom-media-load">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.load()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/semantics-embedded-content.html#dom-htmlmediaelement-load">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.load()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`load`

1

12

3.5

9

≤12.1

3.2

1

18

4

≤12.1

3

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/load" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/load</a>
