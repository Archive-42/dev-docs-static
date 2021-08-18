SpeechSynthesisUtterance.onstart
================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `onstart` property of the [`SpeechSynthesisUtterance`](../speechsynthesisutterance) interface represents an event handler that will run when the utterance has begun to be spoken (when the [start](start_event) event fires.)

This occurs when the [`SpeechSynthesis.speak()`](../speechsynthesis/speak) method is invoked.

Syntax
------

    speechSynthesisUtteranceInstance.onstart = function() { ... };

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

      utterThis.onstart = function(event) {
        console.log('We have started uttering this speech: ' + event.utterance.text);
      }

      inputTxt.blur();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesisutterance-onstart">Web Speech API<br />
<span class="small">The definition of 'onstart' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`onstart`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance/onstart" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance/onstart</a>
