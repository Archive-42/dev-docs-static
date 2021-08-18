SpeechSynthesisVoice.voiceURI
=============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `voiceURI` read-only property of the [`SpeechSynthesisVoice`](../speechsynthesisvoice) interface returns the type of URI and location of the speech synthesis service for this voice.

Syntax
------

    var myVoiceURI = speechSynthesisVoiceInstance.voiceURI;

### Value

A [`DOMString`](../domstring) representing the URI of the voice. This is a generic URI and can point to local or remote services, e.g. it could be a proprietary system URN or a URL to a remote service.

Examples
--------

    for(i = 0; i < voices.length ; i++) {
      var option = document.createElement('option');
      option.textContent = voices[i].name + ' (' + voices[i].lang + ')';

      if(voices[i].default) {
        option.textContent += ' -- DEFAULT';
      }

      console.log(voices[i].voiceURI);
      // On Mac, this returns URNs, for example 'urn:moz-tts:osx:com.apple.speech.synthesis.voice.daniel'

      option.setAttribute('data-lang', voices[i].lang);
      option.setAttribute('data-name', voices[i].name);
      voiceSelect.appendChild(option);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesisvoice-voiceuri">Web Speech API<br />
<span class="small">The definition of 'voiceURI' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

-   [Web Speech API](../web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisVoice/voiceURI" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisVoice/voiceURI</a>
