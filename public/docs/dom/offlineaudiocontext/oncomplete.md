# OfflineAudioContext.oncomplete

The `oncomplete` event handler of the `OfflineAudioContext` interface is called when the audio processing is terminated, that is when the `complete` event (of type [`OfflineAudioCompletionEvent`](../offlineaudiocompletionevent)) is raised.

## Syntax

    var offlineAudioCtx = new OfflineAudioContext();
    offlineAudioCtx.oncomplete = function() { ... }

## Example

When processing is complete, you might want to use the `oncomplete` handler the prompt the user that the audio can now be played, and enable the play button.

    offlineAudioCtx.oncomplete = function() {
      console.log('Offline audio processing now complete');
      showModalDialog('Song processed and ready to play');
      playBtn.disabled = false;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-offlineaudiocontext-oncomplete">Web Audio API<br />
<span class="small">The definition of 'oncomplete' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`oncomplete`

25

12

25

No

15

6

≤37

25

25

14

?

1.5

## See also

- [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext/oncomplete" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext/oncomplete</a>
