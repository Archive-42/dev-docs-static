SpeechSynthesis.onvoiceschanged
===============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `onvoiceschanged` property of the [`SpeechSynthesis`](../speechsynthesis) interface represents an event handler that will run when the list of [`SpeechSynthesisVoice`](../speechsynthesisvoice) objects that would be returned by the [`SpeechSynthesis.getVoices()`](getvoices) method has changed (when the [voiceschanged](voiceschanged_event) event fires.)

This may occur when speech synthesis is being done on the server-side and the voices list is being determined asynchronously, or when client-side voices are installed/uninstalled while a speech synthesis application is running.

Syntax
------

    speechSynthesisInstance.onvoiceschanged = function() { ... };

Examples
--------

This could be used to populate a list of voices that the user can choose between when the event fires (see our [Speak easy synthesis demo](https://github.com/mdn/web-speech-api/blob/gh-pages/speak-easy-synthesis/script.js).) Note that Firefox doesn't support it at present, and will just return a list of voices when [`SpeechSynthesis.getVoices()`](getvoices) is fired. With Chrome however, you have to wait for the event to fire before populating the list, hence the bottom if statement seen below.

    var synth = window.speechSynthesis;
    var voices = [];

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesis-onvoiceschanged">Web Speech API<br />
<span class="small">The definition of 'onvoiceschanged' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`onvoiceschanged`

33

14

49

No

No

No

No

33

62

No

No

3.0

See also
--------

-   [Web Speech API](../web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis/onvoiceschanged" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis/onvoiceschanged</a>
