OfflineAudioContext: complete event
===================================

The `complete` event of the [`OfflineAudioContext`](../offlineaudiocontext) interface is fired when the rendering of an offline audio context is complete.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Default action</td><td>None</td></tr><tr class="even"><td>Interface</td><td><a href="../offlineaudiocompletionevent"><code>OfflineAudioCompletionEvent</code></a></td></tr><tr class="odd"><td>Event handler property</td><td><a href="oncomplete"><code>OfflineAudioContext.oncomplete</code></a></td></tr></tbody></table>

Examples
--------

When processing is complete, you might want to use the `oncomplete` handler the prompt the user that the audio can now be played, and enable the play button:

    let offlineAudioCtx = new OfflineAudioContext();

    offlineAudioCtx.addEventListener('complete', () => {
      console.log('Offline audio processing now complete');
      showModalDialog('Song processed and ready to play');
      playBtn.disabled = false;
    })

You can also set up the event handler using the [`OfflineAudioContext.oncomplete`](oncomplete) property:

    let offlineAudioCtx = new OfflineAudioContext();

    offlineAudioCtx.oncomplete = function() {
      console.log('Offline audio processing now complete');
      showModalDialog('Song processed and ready to play');
      playBtn.disabled = false;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#OfflineAudioCompletionEvent">Web Audio API<br />
<span class="small">The definition of 'OfflineAudioCompletionEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`complete_event`

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

See also
--------

-   [`OfflineAudioContext.oncomplete`](oncomplete)
-   [Web Audio API](../web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext/complete_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext/complete_event</a>
