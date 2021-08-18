SpeechSynthesisErrorEvent
=========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `SpeechSynthesisErrorEvent` interface of the [Web Speech API](web_speech_api) contains information about any errors that occur while processing [`SpeechSynthesisUtterance`](speechsynthesisutterance) objects in the speech service.

Properties
----------

*`SpeechSynthesisErrorEvent` extends the [`SpeechSynthesisEvent`](speechsynthesisevent) interface, which inherits properties from its parent interface, [`Event`](event).*

 [`SpeechSynthesisErrorEvent.error`](speechsynthesiserrorevent/error) <span class="badge inline readonly">Read only </span>   
Returns an error code indicating what has gone wrong with a speech synthesis attempt.

Methods
-------

*`SpeechSynthesisErrorEvent` extends the [`SpeechSynthesisEvent`](speechsynthesisevent) interface, which inherits methods from its parent interface, [`Event`](event).*

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
        console.log('An error has occurred with the speech synthesis: ' + event.error);
      }

      inputTxt.blur();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#speechsynthesiserrorevent">Web Speech API<br />
<span class="small">The definition of 'SpeechSynthesisErrorEvent' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`SpeechSynthesisErrorEvent`

33

≤18

49

No

21

7

No

See [bug 487255](https://crbug.com/487255)

33

62

No

7

3.0

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

-   [Web Speech API](web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisErrorEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisErrorEvent</a>
