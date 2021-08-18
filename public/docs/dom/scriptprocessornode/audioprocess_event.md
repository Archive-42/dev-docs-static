ScriptProcessorNode: audioprocess event
=======================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The audioprocess event of the [`ScriptProcessorNode`](../scriptprocessornode) interface is fired when an input buffer of a script processor is ready to be processed.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Default action</td><td>None</td></tr><tr class="even"><td>Interface</td><td><a href="../audioprocessingevent"><code>AudioProcessingEvent</code></a></td></tr><tr class="odd"><td>Event handler property</td><td><a href="onaudioprocess"><code>ScriptProcessorNode.onaudioprocess</code></a></td></tr></tbody></table>

Examples
--------

    scriptNode.addEventListener('audioprocess', function(audioProcessingEvent) {
      // The input buffer is a song we loaded earlier
      var inputBuffer = audioProcessingEvent.inputBuffer;

      // The output buffer contains the samples that will be modified and played
      var outputBuffer = audioProcessingEvent.outputBuffer;

      // Loop through the output channels (in this case there is only one)
      for (var channel = 0; channel < outputBuffer.numberOfChannels; channel++) {
        var inputData = inputBuffer.getChannelData(channel);
        var outputData = outputBuffer.getChannelData(channel);

        // Loop through the 4096 samples
        for (var sample = 0; sample < inputBuffer.length; sample++) {
          // make output equal to the same as the input
          outputData[sample] = inputData[sample];

          // add noise to each output sample
          outputData[sample] += ((Math.random() * 2) - 1) * 0.2;
        }
      }
    })

You could also set up the event handler using the [`ScriptProcessorNode.onaudioprocess`](onaudioprocess) property:

    scriptNode.onaudioprocess = function(audioProcessingEvent) {
      ...
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://webaudio.github.io/web-audio-api/#AudioProcessingEvent-section">Web Audio API<br />
<span class="small">The definition of 'AudioProcessingEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`audioprocess_event`

14

12

25

No

15

6

≤37

Yes

25

14

6

Yes

See also
--------

-   [`ScriptProcessorNode.onaudioprocess`](onaudioprocess)
-   [Web Audio API](../web_audio_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ScriptProcessorNode/audioprocess_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ScriptProcessorNode/audioprocess_event</a>
