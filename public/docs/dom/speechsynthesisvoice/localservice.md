SpeechSynthesisVoice.localService
=================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `localService` read-only property of the [`SpeechSynthesisVoice`](../speechsynthesisvoice) interface returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the voice is supplied by a local speech synthesizer service (`true`), or a remote speech synthesizer service (`false`.)

This property is provided to allow differentiation in the case that some voice options are provided by a remote service; it is possible that remote voices might have extra latency, bandwidth or cost associated with them, so such distinction may be useful.

Syntax
------

    var amILocal = speechSynthesisVoiceInstance.localService;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean).

Examples
--------

    for(i = 0; i < voices.length ; i++) {
      var option = document.createElement('option');
      option.textContent = voices[i].name + ' (' + voices[i].lang + ')';

      if(voices[i].default) {
        option.textContent += ' -- DEFAULT';
      }

      console.log(voices[i].localService);

      option.setAttribute('data-lang', voices[i].lang);
      option.setAttribute('data-name', voices[i].name);
      voiceSelect.appendChild(option);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesisvoice-localservice">Web Speech API<br />
<span class="small">The definition of 'localService' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

See also
--------

-   [Web Speech API](../web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisVoice/localService" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisVoice/localService</a>
