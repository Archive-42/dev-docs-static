SpeechSynthesisUtterance.rate
=============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `rate` property of the [`SpeechSynthesisUtterance`](../speechsynthesisutterance) interface gets and sets the speed at which the utterance will be spoken at.

If unset, a default value of 1 will be used.

Syntax
------

    var myRate = speechSynthesisUtteranceInstance.rate;
    speechSynthesisUtteranceInstance.rate = 1.5;

### Value

A float representing the rate value. It can range between 0.1 (lowest) and 10 (highest), with 1 being the default pitch for the current platform or voice, which should correspond to a normal speaking rate. Other values act as a percentage relative to this, so for example 2 is twice as fast, 0.5 is half as fast, etc.

Some speech synthesis engines or voices may constrain the minimum and maximum rates further. If [SSML](https://www.w3.org/TR/speech-synthesis/) is used, this value will be overridden by [prosody tags](https://www.w3.org/TR/speech-synthesis/#S3.2.4) in the markup.

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
      utterThis.rate = 1.5;
      synth.speak(utterThis);
      inputTxt.blur();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesisutterance-rate">Web Speech API<br />
<span class="small">The definition of 'rate' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`rate`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance/rate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance/rate</a>
