SpeechSynthesisVoice.default
============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `default` read-only property of the [`SpeechSynthesisVoice`](../speechsynthesisvoice) interface returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the voice is the default voice for the current app (`true`), or not (`false`.)

**Note**: For some devices, it might be the default voice for the voice's language. The spec is not very clear on which it should be, so some implementations may differ.

Syntax
------

    var amIDefault = speechSynthesisVoiceInstance.default;

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

      option.setAttribute('data-lang', voices[i].lang);
      option.setAttribute('data-name', voices[i].name);
      voiceSelect.appendChild(option);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesisvoice-default">Web Speech API<br />
<span class="small">The definition of 'default' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

See also
--------

-   [Web Speech API](../web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisVoice/default" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisVoice/default</a>
