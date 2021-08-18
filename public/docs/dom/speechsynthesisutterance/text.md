SpeechSynthesisUtterance.text
=============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `text` property of the [`SpeechSynthesisUtterance`](../speechsynthesisutterance) interface gets and sets the text that will be synthesised when the utterance is spoken.

The text may be provided as plain text, or a well-formed [SSML](https://www.w3.org/TR/speech-synthesis/) document. The SSML tags will be stripped away by devices that don't support SSML.

Syntax
------

    var myText = speechSynthesisUtteranceInstance.text;
    speechSynthesisUtteranceInstance.text = 'Hello I am speaking';

### Value

A [`DOMString`](../domstring) representing the text to the synthesised. The maximum length of the text that can be spoken in each utterance is 32,767 characters.

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
      console.log(utterThis.text);
      synth.speak(utterThis);
      inputTxt.blur();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesisutterance-text">Web Speech API<br />
<span class="small">The definition of 'text' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`text`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance/text" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance/text</a>
