SpeechSynthesisUtterance.volume
===============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `volume` property of the [`SpeechSynthesisUtterance`](../speechsynthesisutterance) interface gets and sets the volume that the utterance will be spoken at.

If not set, the default value 1 will be used.

Syntax
------

    var myVolume = speechSynthesisUtteranceInstance.volume;
    speechSynthesisUtteranceInstance.volume = 0.5;

### Value

A float that represents the volume value, between 0 (lowest) and 1 (highest.)

If [SSML](https://www.w3.org/TR/speech-synthesis/) is used, this value will be overridden by [prosody tags](https://www.w3.org/TR/speech-synthesis/#S3.2.4) in the markup.

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
      utterThis.volume = 0.5;
      synth.speak(utterThis);
      inputTxt.blur();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesisutterance-volume">Web Speech API<br />
<span class="small">The definition of 'volume' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`volume`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance/volume" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance/volume</a>
