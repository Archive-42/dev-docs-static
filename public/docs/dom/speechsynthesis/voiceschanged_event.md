SpeechSynthesis: voiceschanged event
====================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `voiceschanged` event of the [Web Speech API](../web_speech_api) is fired when the list of [`SpeechSynthesisVoice`](../speechsynthesisvoice) objects that would be returned by the [`SpeechSynthesis.getVoices()`](getvoices) method has changed (when the `voiceschanged` event fires.)

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onvoiceschanged</code></td></tr></tbody></table>

Examples
--------

This could be used to repopulate a list of voices that the user can choose between when the event fires. You can use the `voiceschanged` event in an `addEventListener` method:

    var synth = window.speechSynthesis;

    synth.addEventListener('voiceschanged', function() {
      var voices = synth.getVoices();
      for(i = 0; i < voices.length ; i++) {
        var option = document.createElement('option');
        option.textContent = voices[i].name + ' (' + voices[i].lang + ')';
        option.setAttribute('data-lang', voices[i].lang);
        option.setAttribute('data-name', voices[i].name);
        voiceSelect.appendChild(option);
      }
    });

Or use the `onvoiceschanged` event handler property:

    var synth = window.speechSynthesis;
    synth.onvoiceschanged = function() {
      var voices = synth.getVoices();
      for(i = 0; i < voices.length ; i++) {
        var option = document.createElement('option');
        option.textContent = voices[i].name + ' (' + voices[i].lang + ')';
        option.setAttribute('data-lang', voices[i].lang);
        option.setAttribute('data-name', voices[i].name);
        voiceSelect.appendChild(option);
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#tts-events">Web Speech API<br />
<span class="small">The definition of 'speech synthesis events' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`voiceschanged_event`

33

14

49

No

21

7

No

33

62

No

7

3.0

See also
--------

-   [Web Speech API](../web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis/voiceschanged_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis/voiceschanged_event</a>
