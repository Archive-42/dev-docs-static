SpeechSynthesisErrorEvent.error
===============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `error` property of the [`SpeechSynthesisErrorEvent`](../speechsynthesiserrorevent) interface returns an error code indicating what has gone wrong with a speech synthesis attempt.

Syntax
------

    myError = event.error;

### Value

A [`DOMString`](../domstring) containing an error code. Possible codes are:

canceled  
A [`SpeechSynthesis.cancel`](../speechsynthesis/cancel) method call caused the [`SpeechSynthesisUtterance`](../speechsynthesisutterance) to be removed from the queue before it had begun being spoken.

interrupted  
A [`SpeechSynthesis.cancel`](../speechsynthesis/cancel) method call caused the [`SpeechSynthesisUtterance`](../speechsynthesisutterance) to be interrupted after it had begun being spoken and before it completed.

audio-busy  
The operation couldn't be completed at this time because the user-agent couldn't access the audio output device (for example, the user may need to correct this by closing another application.)

audio-hardware  
The operation couldn't be completed at this time because the user-agent couldn't identify an audio output device (for example, the user may need to connect a speaker or configure system settings.)

network  
The operation couldn't be completed at this time because some required network communication failed.

synthesis-unavailable  
The operation couldn't be completed at this time because no synthesis engine was available (For example, the user may need to install or configure a synthesis engine.)

synthesis-failed  
The operation failed because the synthesis engine raised an error.

language-unavailable  
No appropriate voice was available for the language set in [`SpeechSynthesisUtterance.lang`](../speechsynthesisutterance/lang).

voice-unavailable  
The voice set in [`SpeechSynthesisUtterance.voice`](../speechsynthesisutterance/voice) was not available.

text-too-long  
The contents of the [`SpeechSynthesisUtterance.text`](../speechsynthesisutterance/text) attribute was too long to synthesize.

invalid-argument  
The content of the [`SpeechSynthesisUtterance.rate`](../speechsynthesisutterance/rate), [`SpeechSynthesisUtterance.pitch`](../speechsynthesisutterance/pitch) or [`SpeechSynthesisUtterance.volume`](../speechsynthesisutterance/volume) property was not valid.

Examples
--------

    var synth = window.speechSynthesis;

    var inputForm = document.querySelector('form');
    var inputTxt = document.querySelector('input');
    var voiceSelect = document.querySelector('select');

    var voices = synth.getVoices();

      ...

    inputForm.onsubmit = function(event) {
      event.preventDefault();

      var utterThis = new SpeechSynthesisUtterance(inputTxt.value);
      var selectedOption = voiceSelect.selectedOptions[0].getAttribute('data-name');
      for(i = 0; i < voices.length ; i++) {
        if(voices[i].name === selectedOption) {
          utterThis.voice = voices[i];
        }
      }

      synth.speak(utterThis);

      utterThis.onerror = function(event) {
        console.error('An error has occurred with the speech synthesis: ' + event.error);
      }

      inputTxt.blur();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesiserrorevent-error">Web Speech API<br />
<span class="small">The definition of 'error' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`error`

33

≤18

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisErrorEvent/error" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisErrorEvent/error</a>
