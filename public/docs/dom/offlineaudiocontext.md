OfflineAudioContext
===================

The `OfflineAudioContext` interface is an [`AudioContext`](audiocontext) interface representing an audio-processing graph built from linked together [`AudioNode`](audionode)s. In contrast with a standard [`AudioContext`](audiocontext), an `OfflineAudioContext` doesn't render the audio to the device hardware; instead, it generates it, as fast as it can, and outputs the result to an [`AudioBuffer`](audiobuffer).

Constructor
-----------

[`OfflineAudioContext.OfflineAudioContext()`](offlineaudiocontext/offlineaudiocontext)  
Creates a new `OfflineAudioContext` instance.

Properties
----------

*Also inherits properties from its parent interface, [`BaseAudioContext`](baseaudiocontext).*

 [`OfflineAudioContext.length`](offlineaudiocontext/length) <span class="badge inline readonly">Read only </span>   
An integer representing the size of the buffer in sample-frames.

### Event handlers

[`OfflineAudioContext.oncomplete`](offlineaudiocontext/oncomplete)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) called when processing is terminated, that is when the `complete` event (of type [`OfflineAudioCompletionEvent`](offlineaudiocompletionevent)) is raised, after the event-based version of [`OfflineAudioContext.startRendering()`](offlineaudiocontext/startrendering) is used.

Methods
-------

*Also inherits methods from its parent interface, [`BaseAudioContext`](baseaudiocontext).*

[`OfflineAudioContext.suspend()`](offlineaudiocontext/suspend)  
Schedules a suspension of the time progression in the audio context at the specified time and returns a promise.

[`OfflineAudioContext.startRendering()`](offlineaudiocontext/startrendering)  
Starts rendering the audio, taking into account the current connections and the current scheduled changes. This page covers both the event-based version and the promise-based version.

### Deprecated methods

[`OfflineAudioContext.resume()`](offlineaudiocontext/resume)  
Resumes the progression of time in an audio context that has previously been suspended.

**Note**: The `resume()` method is still available — it is now defined on the [`BaseAudioContext`](baseaudiocontext) interface (see [`AudioContext.resume`](audiocontext/resume)) and thus can be accessed by both the [`AudioContext`](audiocontext) and [`OfflineAudioContext`](offlineaudiocontext) interfaces.

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface:

`complete`  
Fired when the rendering of an offline audio context is complete.  
Also available using the `oncomplete` event handler property.

Examples
--------

In this simple example, we declare both an [`AudioContext`](audiocontext) and an `OfflineAudioContext` object. We use the `AudioContext` to load an audio track via XHR ([`BaseAudioContext.decodeAudioData`](baseaudiocontext/decodeaudiodata)), then the `OfflineAudioContext` to render the audio into an [`AudioBufferSourceNode`](audiobuffersourcenode) and play the track through. After the offline audio graph is set up, you need to render it to an [`AudioBuffer`](audiobuffer) using [`OfflineAudioContext.startRendering`](offlineaudiocontext/startrendering).

When the `startRendering()` promise resolves, rendering has completed and the output `AudioBuffer` is returned out of the promise.

At this point we create another audio context, create an [`AudioBufferSourceNode`](audiobuffersourcenode) inside it, and set its buffer to be equal to the promise `AudioBuffer`. This is then played as part of a simple standard audio graph.

**Note**: For a working example, see our [offline-audio-context-promise](https://mdn.github.io/webaudio-examples/offline-audio-context-promise/) Github repo (see the [source code](https://github.com/mdn/webaudio-examples/tree/master/offline-audio-context-promise) too.)

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#OfflineAudioContext">Web Audio API<br />
<span class="small">The definition of 'OfflineAudioContext' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`OfflineAudioContext`

35

25-57

12

25

No

22

15-44

14.1

6-14.1

4.4.3

≤37-57

35

25-57

25

22

14-43

14.5

6-14.5

3.0

1.5-7.0

`OfflineAudioContext`

35

25-57

≤79

53

No

22

15-44

14.1

6-14.1

4.4.3

≤37-57

35

25-57

53

22

14-43

14.5

6-14.5

3.0

1.5-7.0

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

`length`

51

14

Yes

No

38

14.1

51

51

Yes

41

14.5

5.0

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

`resume`

49

≤18

No

No

36

No

49

49

No

36

No

5.0

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

`suspend`

49

≤18

No

No

36

14.1

49

49

No

36

14.5

5.0

See also
--------

-   [Using the Web Audio API](web_audio_api/using_web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/OfflineAudioContext</a>
