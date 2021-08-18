SpeechSynthesisVoice
====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `SpeechSynthesisVoice` interface of the [Web Speech API](web_speech_api) represents a voice that the system supports. Every `SpeechSynthesisVoice` has its own relative speech service including information about language, name and URI.

Properties
----------

 [`SpeechSynthesisVoice.default`](speechsynthesisvoice/default) <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the voice is the default voice for the current app language (`true`), or not (`false`.)

 [`SpeechSynthesisVoice.lang`](speechsynthesisvoice/lang) <span class="badge inline readonly">Read only </span>   
Returns a BCP 47 language tag indicating the language of the voice.

 [`SpeechSynthesisVoice.localService`](speechsynthesisvoice/localservice) <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the voice is supplied by a local speech synthesizer service (`true`), or a remote speech synthesizer service (`false`.)

 [`SpeechSynthesisVoice.name`](speechsynthesisvoice/name) <span class="badge inline readonly">Read only </span>   
Returns a human-readable name that represents the voice.

 [`SpeechSynthesisVoice.voiceURI`](speechsynthesisvoice/voiceuri) <span class="badge inline readonly">Read only </span>   
Returns the type of URI and location of the speech synthesis service for this voice.

Examples
--------

The following snippet is excerpted from our [Speech synthesiser demo](https://github.com/mdn/web-speech-api/tree/master/speak-easy-synthesis).

    var synth = window.speechSynthesis;
    function populateVoiceList() {
      voices = synth.getVoices();

      for(i = 0; i < voices.length ; i++) {
        var option = document.createElement('option');
        option.textContent = voices[i].name + ' (' + voices[i].lang + ')';

        if(voices[i].default) {
          option.textContent += ' -- DEFAULT';
        }

        option.setAttribute('data-lang', voices[i].lang);
        option.setAttribute('data-name', voices[i].name);
        voiceSelect.appendChild(option);
      }
    }

    populateVoiceList();
    if (speechSynthesis.onvoiceschanged !== undefined) {
      speechSynthesis.onvoiceschanged = populateVoiceList;
    }

    inputForm.onsubmit = function(event) {
      event.preventDefault();

      var utterThis = new SpeechSynthesisUtterance(inputTxt.value);
      var selectedOption = voiceSelect.selectedOptions[0].getAttribute('data-name');
      for(i = 0; i < voices.length ; i++) {
        if(voices[i].name === selectedOption) {
          utterThis.voice = voices[i];
        }
      }
      utterThis.pitch = pitch.value;
      utterThis.rate = rate.value;
      synth.speak(utterThis);

      utterThis.onpause = function(event) {
        var char = event.utterance.text.charAt(event.charIndex);
        console.log('Speech paused at character ' + event.charIndex + ' of "' +
        event.utterance.text + '", which is "' + char + '".');
      }

      inputTxt.blur();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#speechsynthesisvoice">Web Speech API<br />
<span class="small">The definition of 'SpeechSynthesisVoice' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`SpeechSynthesisVoice`

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

`default`

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

`lang`

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

`localService`

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

`name`

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

`voiceURI`

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

-   [Web Speech API](web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisVoice" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisVoice</a>
