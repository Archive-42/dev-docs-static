Window.speechSynthesis
======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `speechSynthesis` read-only property of the Window object returns a [`SpeechSynthesis`](../speechsynthesis) object, which is the entry point into using [Web Speech API](../web_speech_api) speech synthesis functionality.

Syntax
------

    var synth = window.speechSynthesis;

### Value

A [`SpeechSynthesis`](../speechsynthesis) object.

Examples
--------

In our basic [Speech synthesiser demo](https://github.com/mdn/web-speech-api/tree/master/speak-easy-synthesis), we first grab a reference to the SpeechSynthesis controller using `window.speechSynthesis`. After defining some necessary variables, we retrieve a list of the voices available using [`SpeechSynthesis.getVoices()`](../speechsynthesis/getvoices) and populate a select menu with them so the user can choose what voice they want.

Inside the `inputForm.onsubmit` handler, we stop the form submitting with [preventDefault()](../event/preventdefault), create a new [`SpeechSynthesisUtterance`](../speechsynthesisutterance) instance containing the text from the text [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), set the utterance's voice to the voice selected in the [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element, and start the utterance speaking via the [`SpeechSynthesis.speak()`](../speechsynthesis/speak) method.

    var synth = window.speechSynthesis;

    var inputForm = document.querySelector('form');
    var inputTxt = document.querySelector('input');
    var voiceSelect = document.querySelector('select');

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
      synth.speak(utterThis);
      inputTxt.blur();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#tts-section">Web Speech API<br />
<span class="small">The definition of 'SpeechSynthesis' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`speechSynthesis`

33

14

49

No

Yes

7

No

See [bug 487255](https://crbug.com/487255)

Yes

No

No

7

Yes

See also
--------

-   [Web Speech API](../web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/speechSynthesis" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/speechSynthesis</a>
