SpeechSynthesisUtterance.voice
==============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `voice` property of the [`SpeechSynthesisUtterance`](../speechsynthesisutterance) interface gets and sets the voice that will be used to speak the utterance.

This should be set to one of the [`SpeechSynthesisVoice`](../speechsynthesisvoice) objects returned by [`SpeechSynthesis.getVoices()`](../speechsynthesis/getvoices). If not set by the time the utterance is spoken, the voice used will be the most suitable default voice available for the utterance's [`lang`](lang) setting.

Syntax
------

    var myVoice = speechSynthesisUtteranceInstance.voice;
    speechSynthesisUtteranceInstance.voice = speechSynthesisVoiceInstance;

### Value

A [`SpeechSynthesisVoice`](../speechsynthesisvoice) object.

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
      inputTxt.blur();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesisutterance-voice">Web Speech API<br />
<span class="small">The definition of 'voice' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`voice`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance/voice" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance/voice</a>
