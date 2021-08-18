HTMLMediaElement.play()
=======================

The [`HTMLMediaElement`](../htmlmediaelement) `play()` method attempts to begin playback of the media. It returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is resolved when playback has been successfully started. Failure to begin playback for any reason, such as permission issues, result in the promise being rejected.

Syntax
------

    var promise = HTMLMediaElement.play();

### Parameters

None.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which is resolved when playback has been started, or is rejected if for any reason playback cannot be started.

**Note:** Older browsers may not return a value from `play()`.

### Exceptions

The promise's **rejection handler** is called with an exception name passed in as its sole input parameter (as opposed to a traditional exception being thrown). Possible errors include:

`NotAllowedError`  
The user agent (browser) or operating system doesn't allow playback of media in the current context or situation. This may happen, for example, if the browser requires the user to explicitly start media playback by clicking a "play" button.

`NotSupportedError`  
The media source (which may be specified as a [`MediaStream`](../mediastream), [`MediaSource`](../mediasource), [`Blob`](../blob), or [`File`](../file), for example) doesn't represent a supported media format.

Other exceptions may be reported, depending on browser implementation details, media player implementation, and so forth.

Usage notes
-----------

Although the term "autoplay" is usually thought of as referring to pages that immediately begin playing media upon being loaded, web browsers' autoplay policies also apply to any script-initiated playback of media, including calls to `play()`.

If the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) is configured not to allow automatic or script-initiated playback of media, calling `play()` will cause the returned promise to be immediately rejected with a `NotAllowedError`. Web sites should be prepared to handle this situation. For example, a site should not present a user interface that assumes playback has begun automatically, but should instead update their UI based on whether the returned promise is resolved or rejected. See the [example](#example) below for more information.

**Note:** The `play()` method may cause the user to be asked to grant permission to play the media, resulting in a possible delay before the returned promise is resolved. Be sure your code doesn't expect an immediate response.

For even more in-depth information about autoplay and autoplay blocking, see our article [Autoplay guide for media and Web Audio APIs](https://developer.mozilla.org/en-US/docs/Web/Media/Autoplay_guide).

Example
-------

This example demonstrates how to confirm that playback has begun and how to gracefully handle blocked automatic playback:

    let videoElem = document.getElementById("video");
    let playButton = document.getElementById("playbutton");

    playButton.addEventListener("click", handlePlayButton, false);
    playVideo();

    async function playVideo() {
      try {
        await videoElem.play();
        playButton.classList.add("playing");
      } catch(err) {
        playButton.classList.remove("playing");
      }
    }

    function handlePlayButton() {
      if (videoElem.paused) {
        playVideo();
      } else {
        videoElem.pause();
        playButton.classList.remove("playing");
      }
    }

In this example, playback of video is toggled off and on by the `async` `playVideo()` function. It tries to play the video, and if successful sets the class name of the `playButton` element to `"playing"`. If playback fails to start, the `playButton` element's class is cleared, restoring its default appearance. This ensures that the play button matches the actual state of playback by watching for the resolution or rejection of the [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) returned by `play()`.

When this example is executed, it begins by collecting references to the [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) element as well as the [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) used to toggle playback on and off. It then sets up an event handler for the `click` event on the play toggle button and attempts to automatically begin playback by calling `playVideo()`.

You can [try out or remix this example in real time on Glitch](https://media-play-promise.glitch.me/).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#dom-media-play">HTML Living Standard<br />
<span class="small">The definition of 'play()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition; living specification.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#dom-media-play">HTML5<br />
<span class="small">The definition of 'play()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

**Note:** The WHATWG and W3C versions of the specification differ (as of August, 2018) as to whether this method returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) or nothing at all, respectively.

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

`play`

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

`returns_promise`

50

17

53

No

37

10

50

50

53

37

10

5.0

See also
--------

-   [Web media technologies](https://developer.mozilla.org/en-US/docs/Web/Media)
-   Learning: [Video and audio content](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Video_and_audio_content)
-   [Autoplay guide for media and Web Audio APIs](https://developer.mozilla.org/en-US/docs/Web/Media/Autoplay_guide)
-   [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/play" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/play</a>
