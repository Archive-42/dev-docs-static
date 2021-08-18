SpeechSynthesisUtterance
========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `SpeechSynthesisUtterance` interface of the [Web Speech API](web_speech_api) represents a speech request. It contains the content the speech service should read and information about how to read it (e.g. language, pitch and volume.)

Constructor
-----------

[`SpeechSynthesisUtterance.SpeechSynthesisUtterance()`](speechsynthesisutterance/speechsynthesisutterance)  
Returns a new `SpeechSynthesisUtterance` object instance.

Properties
----------

*`SpeechSynthesisUtterance` also inherits properties from its parent interface, [`EventTarget`](eventtarget).*

[`SpeechSynthesisUtterance.lang`](speechsynthesisutterance/lang)  
Gets and sets the language of the utterance.

[`SpeechSynthesisUtterance.pitch`](speechsynthesisutterance/pitch)  
Gets and sets the pitch at which the utterance will be spoken at.

[`SpeechSynthesisUtterance.rate`](speechsynthesisutterance/rate)  
Gets and sets the speed at which the utterance will be spoken at.

[`SpeechSynthesisUtterance.text`](speechsynthesisutterance/text)  
Gets and sets the text that will be synthesised when the utterance is spoken.

[`SpeechSynthesisUtterance.voice`](speechsynthesisutterance/voice)  
Gets and sets the voice that will be used to speak the utterance.

[`SpeechSynthesisUtterance.volume`](speechsynthesisutterance/volume)  
Gets and sets the volume that the utterance will be spoken at.

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

`boundary`  
Fired when the spoken utterance reaches a word or sentence boundary.  
Also available via the `onboundary` property.

`end`  
Fired when the utterance has finished being spoken.  
Also available via the `onend` property.

`error`  
Fired when an error occurs that prevents the utterance from being successfully spoken.  
Also available via the `onerror` property

`mark`  
Fired when the spoken utterance reaches a named SSML "mark" tag.  
Also available via the `onmark` property.

`pause`  
Fired when the utterance is paused part way through.  
Also available via the `onpause` property.

`resume`  
Fired when a paused utterance is resumed.  
Also available via the `onresume` property.

`start`  
Fired when the utterance has begun to be spoken.  
Also available via the `onstart` property.

Examples
--------

In our basic [Speech synthesiser demo](https://mdn.github.io/web-speech-api/speak-easy-synthesis/) ([source](https://github.com/mdn/web-speech-api/tree/master/speak-easy-synthesis)), we first grab a reference to the SpeechSynthesis controller using `window.speechSynthesis`. After defining some necessary variables, we retrieve a list of the voices available using [`SpeechSynthesis.getVoices()`](speechsynthesis/getvoices) and populate a select menu with them so the user can choose what voice they want.

Inside the `inputForm.onsubmit` handler, we stop the form submitting with [`preventDefault()`](event/preventdefault), use the [`constructor`](speechsynthesisutterance/speechsynthesisutterance) to create a new utterance instance containing the text from the text [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), set the utterance's [`voice`](speechsynthesisutterance/voice) to the voice selected in the [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element, and start the utterance speaking via the [`SpeechSynthesis.speak()`](speechsynthesis/speak) method.

    var synth = window.speechSynthesis;
    var voices = synth.getVoices();

    var inputForm = document.querySelector('form');
    var inputTxt = document.querySelector('input');
    var voiceSelect = document.querySelector('select');

    for(var i = 0; i < voices.length; i++) {
      var option = document.createElement('option');
      option.textContent = voices[i].name + ' (' + voices[i].lang + ')';
      option.value = i;
      voiceSelect.appendChild(option);
    }

    inputForm.onsubmit = function(event) {
      event.preventDefault();

      var utterThis = new SpeechSynthesisUtterance(inputTxt.value);
      utterThis.voice = voices[voiceSelect.value];
      synth.speak(utterThis);
      inputTxt.blur();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#tts-section">Web Speech API<br />
<span class="small">The definition of 'SpeechSynthesisUtterance' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`SpeechSynthesisUtterance`

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

`SpeechSynthesisUtterance`

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

`boundary_event`

33

14

49

No

21

7

No

33

The `boundary` event does not fire as expected. See [bug 1122143](https://crbug.com/1122143).

62

No

7

3.0

`end_event`

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

`error_event`

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

`mark_event`

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

`onboundary`

33

14

49

No

21

7

No

33

The `boundary` event does not fire as expected. See [bug 1122143](https://crbug.com/1122143).

62

No

7

3.0

`onend`

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

`onerror`

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

`onmark`

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

`onpause`

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

`onresume`

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

`onstart`

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

`pause_event`

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

`pitch`

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

`resume_event`

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

`start_event`

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

`text`

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

`voice`

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

`volume`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesisUtterance</a>
