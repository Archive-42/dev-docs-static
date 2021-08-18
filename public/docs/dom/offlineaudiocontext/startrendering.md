OfflineAudioContext.startRendering()
====================================

The `startRendering()` method of the [`OfflineAudioContext`](../offlineaudiocontext) Interface starts rendering the audio graph, taking into account the current connections and the current scheduled changes.

The `complete` event (of type [`OfflineAudioCompletionEvent`](../offlineaudiocompletionevent)) is raised when the rendering is finished, containing the resulting [`AudioBuffer`](../audiobuffer) in its `renderedBuffer` property.

Browsers currently support two versions of the `startRendering()` method — an older event-based version and a newer promise-based version. The former will eventually be removed, but currently both mechanisms are provided for legacy reasons.

Syntax
------

Event-based version:

    offlineAudioCtx.startRendering();
    offlineAudioCtx.oncomplete = function(e) {
      // e.renderedBuffer contains the output buffer
    }

Promise-based version:

    offlineAudioCtx.startRendering().then(function(buffer) {
      // buffer contains the output buffer
    });

### Parameters

None.

### Returns

Void.

Example
-------

In this simple example, we declare both an [`AudioContext`](../audiocontext) and an `OfflineAudioContext` object. We use the `AudioContext` to load an audio track via XHR ([`BaseAudioContext.decodeAudioData`](../baseaudiocontext/decodeaudiodata)), then the `OfflineAudioContext` to render the audio into an [`AudioBufferSourceNode`](../audiobuffersourcenode) and play the track through. After the offline audio graph is set up, you need to render it to an [`AudioBuffer`](../audiobuffer) using [`OfflineAudioContext.startRendering`](startrendering).

When the `startRendering()` promise resolves, rendering has completed and the output `AudioBuffer` is returned out of the promise.

At this point we create another audio context, create an [`AudioBufferSourceNode`](../audiobuffersourcenode) inside it, and set its buffer to be equal to the promise `AudioBuffer`. This is then played as part of a simple standard audio graph.

**Note**: For a working example, see our [offline-audio-context-promise](https://mdn.github.io/webaudio-examples/offline-audio-context-promise/) Github repo (see the [source code](https://github.com/mdn/webaudio-examples) too.)

    // define online and offline audio context

    var audioCtx = new AudioContext();
    var offlineCtx = new OfflineAudioContext(2,44100*40,44100);

    source = offlineCtx.createBufferSource();

    // use XHR to load an audio track, and
    // decodeAudioData to decode it and OfflineAudioContext to render it

    function getData() {
      request = new XMLHttpRequest();

      request.open('GET', 'viper.ogg', true);

      request.responseType = 'arraybuffer';

      request.onload = function() {
        var audioData = request.response;

        audioCtx.decodeAudioData(audioData, function(buffer) {
          myBuffer = buffer;
          source.buffer = myBuffer;
          source.connect(offlineCtx.destination);
          source.start();
          //source.loop = true;
          offlineCtx.startRendering().then(function(renderedBuffer) {
            console.log('Rendering completed successfully');
            var audioCtx = new (window.AudioContext || window.webkitAudioContext)();
            var song = audioCtx.createBufferSource();
            song.buffer = renderedBuffer;

            song.connect(audioCtx.destination);

            play.onclick = function() {
              song.start();
            }
          }).catch(function(err) {
              console.log('Rendering failed: ' + err);
              // Note: The promise should reject when startRendering is called a second time on an OfflineAudioContext
          });
        });
      }

      request.send();
    }

    // Run getData to start the process off

    getData();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#dom-offlineaudiocontext-startrendering">Web Audio API<br />
<span class="small">The definition of 'startRendering()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`startRendering`

25

12

25

No

15

14.1

6-14.1

≤37

25

25

14

14.5

6-14.5

1.5

`Promise_based_startRendering`

42

≤18

37

No

29

14.1

42

42

37

29

14.5

4.0

See also
--------

-   [Using the Web Audio API](../web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext/startRendering" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext/startRendering</a>
