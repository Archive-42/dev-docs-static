VideoTrack
==========

The [`VideoTrack`](videotrack) interface represents a single video track from a [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element. The most common use for accessing a `VideoTrack` object is to toggle its [`selected`](videotrack/selected) property in order to make it the active video track for its [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element.

Properties
----------

[`selected`](videotrack/selected)  
A Boolean value which controls whether or not the video track is active. Only a single video track can be active at any given time, so setting this property to `true` for one track while another track is active will make that other track inactive.

 [`id`](videotrack/id) <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) which uniquely identifies the track within the media. This ID can be used to locate a specific track within a video track list by calling [`VideoTrackList.getTrackById()`](videotracklist/gettrackbyid). The ID can also be used as the fragment part of the URL if the media supports seeking by media fragment per the [Media Fragments URI specification](https://www.w3.org/TR/media-frags/).

 [`kind`](videotrack/kind) <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) specifying the category into which the track falls. For example, the main video track would have a `kind` of `"main"`.

 [`label`](videotrack/label) <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) providing a human-readable label for the track. For example, a track whose `kind` is `"sign"` might have a `label` of `"A sign-language interpretation"`. This string is empty if no label is provided.

 [`language`](videotrack/language) <span class="badge inline readonly">Read only </span>   
A [`DOMString`](domstring) specifying the video track's primary language, or an empty string if unknown. The language is specified as a BCP 47 ([RFC 5646](https://tools.ietf.org/html/rfc5646)) language code, such as `"en-US"` or `"pt-BR"`.

 [`sourceBuffer`](videotrack/sourcebuffer) <span class="badge inline readonly">Read only </span>   
The [`SourceBuffer`](sourcebuffer) that created the track. Returns null if the track was not created by a [`SourceBuffer`](sourcebuffer) or the [`SourceBuffer`](sourcebuffer) has been removed from the [`MediaSource.sourceBuffers`](mediasource/sourcebuffers) attribute of its parent media source.

Usage notes
-----------

To get a `VideoTrack` for a given media element, use the element's [`videoTracks`](htmlmediaelement/videotracks) property, which returns a [`VideoTrackList`](videotracklist) object from which you can get the individual tracks contained in the media:

    var el = document.querySelector("video");
    var tracks = el.videoTracks;

You can then access the media's individual tracks using either array syntax or functions such as [`forEach()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach).

This first example gets the first video track on the media:

    var firstTrack = tracks[0];

The next example scans through all of the media's video tracks, activating the first video track that is in the user's preferred language (taken from a variable `userLanguage`).

    for (var i = 0; i < tracks.length; i++) {
      if (tracks[i].language === userLanguage) {
        tracks[i].selected = true;
        break;
      }
    });

The [`language`](videotrack/language) is in standard ([RFC 5646](https://tools.ietf.org/html/rfc5646)) format. For US English, this would be `"en-US"`, for example.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#videotrack">HTML Living Standard<br />
<span class="small">The definition of 'VideoTrack' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

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

`VideoTrack`

37

79

12-79

33

10

24

6.1

No

37

33

24

7

No

`id`

37

79

12-79

33

10

24

6.1

No

37

33

24

7

No

`kind`

37

79

12-79

33

10

24

6.1

No

37

33

24

7

No

`label`

37

79

12-79

33

10

24

6.1

No

37

33

24

7

No

`language`

37

79

12-79

33

10

24

6.1

No

37

33

24

7

No

`selected`

37

79

12-79

33

10

24

6.1

No

37

33

24

7

No

`sourceBuffer`

51

79

12-79

No

No

38

6.1

No

51

No

41

7

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/VideoTrack" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/VideoTrack</a>
