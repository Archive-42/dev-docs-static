# HTMLMediaElement.autoplay

The `HTMLMediaElement.autoplay` property reflects the [`autoplay`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video#attr-autoplay) HTML attribute, indicating whether playback should automatically begin as soon as enough media is available to do so without interruption.

A media element whose source is a [`MediaStream`](../mediastream) and whose `autoplay` property is `true` will begin playback when it becomes active (that is, when [`MediaStream.active`](../mediastream/active) becomes `true`).

**Note:** Sites which automatically play audio (or videos with an audio track) can be an unpleasant experience for users, so it should be avoided when possible. If you must offer autoplay functionality, you should make it opt-in (requiring a user to specifically enable it). However, autoplay can be useful when creating media elements whose source will be set at a later time, under user control.

For a much more in-depth look at autoplay, autoplay blocking, and how to respond when autoplay is blocked by the user's browser, see our article [Autoplay guide for media and Web Audio APIs](https://developer.mozilla.org/en-US/docs/Web/Media/Autoplay_guide).

## Syntax

    HTMLMediaElement.autoplay = true | false;

    var autoplay = HTMLMediaElement.autoplay;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) whose value is `true` if the media element will begin playback as soon as enough content has loaded to allow it to do so without interruption.

**Note:** Some browsers offer users the ability to override `autoplay` in order to prevent disruptive audio or video from playing without permission or in the background. Do not rely on `autoplay` actually starting playback and instead use [`play`](play_event) event.

## Examples

...

    <video id="video" controls>
      <source src="https://player.vimeo.com/external/250688977.sd.mp4?s=d14b1f1a971dde13c79d6e436b88a6a928dfe26b&profile_id=165">
    </video>

    *** Disable autoplay (recommended) ***
          false is the default value
            document.querySelector('#video').autoplay = false;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/embedded-content.html#dom-media-autoplay">HTML Living Standard<br />
<span class="small">The definition of 'HTMLMediaElement.autoplay' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#htmlmediaelement">HTML5<br />
<span class="small">The definition of 'HTMLMediaElement.autoplay' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`autoplay`

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

## See also

- The interface defining it, [`HTMLMediaElement`](../htmlmediaelement).
- The [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) and [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) elements

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/autoplay" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLMediaElement/autoplay</a>
