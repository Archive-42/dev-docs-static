SpeechSynthesis
===============

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `SpeechSynthesis` interface of the [Web Speech API](web_speech_api) is the controller interface for the speech service; this can be used to retrieve information about the synthesis voices available on the device, start and pause speech, and other commands besides.

Properties
----------

*`SpeechSynthesis` also inherits properties from its parent interface, [`EventTarget`](eventtarget).*

 [`SpeechSynthesis.paused`](speechsynthesis/paused) <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that returns `true` if the `SpeechSynthesis` object is in a paused state.

 [`SpeechSynthesis.pending`](speechsynthesis/pending) <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that returns `true` if the utterance queue contains as-yet-unspoken utterances.

 [`SpeechSynthesis.speaking`](speechsynthesis/speaking) <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that returns `true` if an utterance is currently in the process of being spoken — even if `SpeechSynthesis` is in a paused state.

Methods
-------

*`SpeechSynthesis` also inherits methods from its parent interface, [`EventTarget`](eventtarget).*

[`SpeechSynthesis.cancel()`](speechsynthesis/cancel)  
Removes all utterances from the utterance queue.

[`SpeechSynthesis.getVoices()`](speechsynthesis/getvoices)  
Returns a list of [`SpeechSynthesisVoice`](speechsynthesisvoice) objects representing all the available voices on the current device.

[`SpeechSynthesis.pause()`](speechsynthesis/pause)  
Puts the `SpeechSynthesis` object into a paused state.

[`SpeechSynthesis.resume()`](speechsynthesis/resume)  
Puts the `SpeechSynthesis` object into a non-paused state: resumes it if it was already paused.

[`SpeechSynthesis.speak()`](speechsynthesis/speak)  
Adds an [`utterance`](speechsynthesisutterance) to the utterance queue; it will be spoken when any other utterances queued before it have been spoken.

Events
------

Listen to this event using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

`voiceschanged`  
Fired when the list of [`SpeechSynthesisVoice`](speechsynthesisvoice) objects that would be returned by the [`SpeechSynthesis.getVoices()`](speechsynthesis/getvoices) method has changed.  
Also available via the `onvoiceschanged` property.

Examples
--------

First, a simple example:

    let utterance = new SpeechSynthesisUtterance("Hello world!");
    speechSynthesis.speak(utterance);

Now we'll look at a more fully-fledged example. In our [Speech synthesiser demo](https://github.com/mdn/web-speech-api/tree/master/speak-easy-synthesis), we first grab a reference to the SpeechSynthesis controller using `window.speechSynthesis`. After defining some necessary variables, we retrieve a list of the voices available using [`SpeechSynthesis.getVoices()`](speechsynthesis/getvoices) and populate a select menu with them so the user can choose what voice they want.

Inside the `inputForm.onsubmit` handler, we stop the form submitting with [preventDefault()](event/preventdefault), create a new [`SpeechSynthesisUtterance`](speechsynthesisutterance) instance containing the text from the text [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), set the utterance's voice to the voice selected in the [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element, and start the utterance speaking via the [`SpeechSynthesis.speak()`](speechsynthesis/speak) method.

    var synth = window.speechSynthesis;

    var inputForm = document.querySelector('form');
    var inputTxt = document.querySelector('.txt');
    var voiceSelect = document.querySelector('select');

    var pitch = document.querySelector('#pitch');
    var pitchValue = document.querySelector('.pitch-value');
    var rate = document.querySelector('#rate');
    var rateValue = document.querySelector('.rate-value');

    var voices = [];

    function populateVoiceList() {
      voices = synth.getVoices();

      for(var i = 0; i < voices.length ; i++) {
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
      for(var i = 0; i < voices.length ; i++) {
        if(voices[i].name === selectedOption) {
          utterThis.voice = voices[i];
        }
      }
      utterThis.pitch = pitch.value;
      utterThis.rate = rate.value;
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

`SpeechSynthesis`

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

`cancel`

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

`pause`

33

14

49

No

21

7

No

33

In Android, `pause()` ends the current utterance. `pause()` behaves the same as `cancel()`.

62

In Android, `pause()` ends the current utterance. `pause()` behaves the same as `cancel()`.

No

7

3.0

In Android, `pause()` ends the current utterance. `pause()` behaves the same as `cancel()`.

`paused`

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

`pending`

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

`resume`

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

`speaking`

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

`voiceschanged_event`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechSynthesis</a>
