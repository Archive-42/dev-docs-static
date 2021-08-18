SpeechSynthesis.getVoices()
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `getVoices()` method of the [`SpeechSynthesis`](../speechsynthesis) interface returns a list of [`SpeechSynthesisVoice`](../speechsynthesisvoice) objects representing all the available voices on the current device.

Syntax
------

    speechSynthesisInstance.getVoices();

### Parameters

None.

### Return value

A list (array) of [`SpeechSynthesisVoice`](../speechsynthesisvoice) objects.

**Note**: The spec wrongly lists this method as returning as a `SpeechSynthesisVoiceList` object, but this was in fact removed from the spec.

Example
-------

### JavaScript

    function populateVoiceList() {
      if(typeof speechSynthesis === 'undefined') {
        return;
      }

      var voices = speechSynthesis.getVoices();

      for(var i = 0; i < voices.length; i++) {
        var option = document.createElement('option');
        option.textContent = voices[i].name + ' (' + voices[i].lang + ')';

        if(voices[i].default) {
          option.textContent += ' -- DEFAULT';
        }

        option.setAttribute('data-lang', voices[i].lang);
        option.setAttribute('data-name', voices[i].name);
        document.getElementById("voiceSelect").appendChild(option);
      }
    }

    populateVoiceList();
    if (typeof speechSynthesis !== 'undefined' && speechSynthesis.onvoiceschanged !== undefined) {
      speechSynthesis.onvoiceschanged = populateVoiceList;
    }

### HTML

    <select id="voiceSelect"></select>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesis-getvoices">Web Speech API<br />
<span class="small">The definition of 'getVoices()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`getVoices`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis/getVoices" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis/getVoices</a>
