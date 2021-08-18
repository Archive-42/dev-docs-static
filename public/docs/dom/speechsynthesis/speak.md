SpeechSynthesis.speak()
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `speak()` method of the [`SpeechSynthesis`](../speechsynthesis) interface adds an [`utterance`](../speechsynthesisutterance) to the utterance queue; it will be spoken when any other utterances queued before it have been spoken.

Syntax
------

    speechSynthesisInstance.speak(utterance);

### Returns

Void.

### Parameters

utterance  
A [`SpeechSynthesisUtterance`](../speechsynthesisutterance) object.

Examples
--------

This snippet is excerpted from our [Speech synthesiser demo](https://github.com/mdn/web-speech-api/tree/master/speak-easy-synthesis). When a form containing the text we want to speak is submitted, we (amongst other things) create a new utterance containing this text, then speak it by passing it into `speak()` as a parameter.

    var synth = window.speechSynthesis;

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
      inputTxt.blur();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechsynthesis-speak">Web Speech API<br />
<span class="small">The definition of 'speak()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`speak`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis/speak" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis/speak</a>
