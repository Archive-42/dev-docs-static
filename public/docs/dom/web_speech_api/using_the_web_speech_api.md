Using the Web Speech API
========================

The Web Speech API provides two distinct areas of functionality — speech recognition, and speech synthesis (also known as text to speech, or tts) — which open up interesting new possibilities for accessibility, and control mechanisms. This article provides a simple introduction to both areas, along with demos.

Speech recognition
------------------

Speech recognition involves receiving speech through a device's microphone, which is then checked by a speech recognition service against a list of grammar (basically, the vocabulary you want to have recognized in a particular app.) When a word or phrase is successfully recognized, it is returned as a result (or list of results) as a text string, and further actions can be initiated as a result.

The Web Speech API has a main controller interface for this — [`SpeechRecognition`](../speechrecognition) — plus a number of closely-related interfaces for representing grammar, results, etc. Generally, the default speech recognition system available on the device will be used for the speech recognition — most modern OSes have a speech recognition system for issuing voice commands. Think about Dictation on macOS, Siri on iOS, Cortana on Windows 10, Android Speech, etc.

**Note**: On some browsers, like Chrome, using Speech Recognition on a web page involves a server-based recognition engine. Your audio is sent to a web service for recognition processing, so it won't work offline.

### Demo

To show simple usage of Web speech recognition, we've written a demo called [Speech color changer](https://github.com/mdn/web-speech-api/tree/master/speech-color-changer). When the screen is tapped/clicked, you can say an HTML color keyword, and the app's background color will change to that color.

<img src="data:image/png;base64,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" alt="The UI of an app titled Speech Color changer. It invites the user to tap the screen and say a color, and then it turns the background of the app that color. In this case it has turned the background red." width="300" height="533" />

To run the demo, you can clone (or [directly download](https://github.com/mdn/web-speech-api/archive/master.zip)) the Github repo it is part of, open the HTML index file in a supporting desktop browser, or navigate to the [live demo URL](https://mdn.github.io/web-speech-api/speech-color-changer/) in a supporting mobile browser like Chrome.

### Browser support

Support for Web Speech API speech recognition is currently limited to Chrome for Desktop and Android — Chrome has supported it since around version 33 but with prefixed interfaces, so you need to include prefixed versions of them, e.g. `webkitSpeechRecognition`.

### HTML and CSS

The HTML and CSS for the app is really trivial. We have a title, instructions paragraph, and a div into which we output diagnostic messages.

    <h1>Speech color changer</h1>
    <p>Tap/click then say a color to change the background color of the app.</p>
    <div>
      <p class="output"><em>...diagnostic messages</em></p>
    </div>

The CSS provides a very simple responsive styling so that it looks ok across devices.

### JavaScript

Let's look at the JavaScript in a bit more detail.

#### Chrome support

As mentioned earlier, Chrome currently supports speech recognition with prefixed properties, therefore at the start of our code we include these lines to feed the right objects to Chrome, and any future implementations that might support the features without a prefix:

    var SpeechRecognition = SpeechRecognition || webkitSpeechRecognition
    var SpeechGrammarList = SpeechGrammarList || webkitSpeechGrammarList
    var SpeechRecognitionEvent = SpeechRecognitionEvent || webkitSpeechRecognitionEvent

#### The grammar

The next part of our code defines the grammar we want our app to recognize. The following variable is defined to hold our grammar:

    var colors = [ 'aqua' , 'azure' , 'beige', 'bisque', 'black', 'blue', 'brown', 'chocolate', 'coral' ... ];
    var grammar = '#JSGF V1.0; grammar colors; public <color> = ' + colors.join(' | ') + ' ;'

The grammar format used is [JSpeech Grammar Format](https://www.w3.org/TR/jsgf/) (**JSGF**) — you can find a lot more about it at the previous link to its spec. However, for now let's just run through it quickly:

-   The lines are separated by semi-colons, just like in JavaScript.
-   The first line — `#JSGF V1.0;` — states the format and version used. This always needs to be included first.
-   The second line indicates a type of term that we want to recognize. `public` declares that it is a public rule, the string in angle brackets defines the recognized name for this term (`color`), and the list of items that follow the equals sign are the alternative values that will be recognized and accepted as appropriate values for the term. Note how each is separated by a pipe character.
-   You can have as many terms defined as you want on separate lines following the above structure, and include fairly complex grammar definitions. For this basic demo, we are just keeping things simple.

#### Plugging the grammar into our speech recognition

The next thing to do is define a speech recogntion instance to control the recognition for our application. This is done using the [`SpeechRecognition()`](../speechrecognition/speechrecognition) constructor. We also create a new speech grammar list to contain our grammar, using the [`SpeechGrammarList()`](../speechgrammarlist/speechgrammarlist) constructor.

    var recognition = new SpeechRecognition();
    var speechRecognitionList = new SpeechGrammarList();

We add our `grammar` to the list using the [`SpeechGrammarList.addFromString()`](../speechgrammarlist/addfromstring) method. This accepts as parameters the string we want to add, plus optionally a weight value that specifies the importance of this grammar in relation of other grammars available in the list (can be from 0 to 1 inclusive.) The added grammar is available in the list as a [`SpeechGrammar`](../speechgrammar) object instance.

    speechRecognitionList.addFromString(grammar, 1);

We then add the [`SpeechGrammarList`](../speechgrammarlist) to the speech recognition instance by setting it to the value of the [`SpeechRecognition.grammars`](../speechrecognition/grammars) property. We also set a few other properties of the recognition instance before we move on:

-   [`SpeechRecognition.continuous`](../speechrecognition/continuous): Controls whether continuous results are captured (`true`), or just a single result each time recognition is started (`false`).
-   [`SpeechRecognition.lang`](../speechrecognition/lang): Sets the language of the recognition. Setting this is good practice, and therefore recommended.
-   [`SpeechRecognition.interimResults`](../speechrecognition/interimresults): Defines whether the speech recognition system should return interim results, or just final results. Final results are good enough for this simple demo.
-   [`SpeechRecognition.maxAlternatives`](../speechrecognition/maxalternatives): Sets the number of alternative potential matches that should be returned per result. This can sometimes be useful, say if a result is not completely clear and you want to display a list if alternatives for the user to choose the correct one from. But it is not needed for this simple demo, so we are just specifying one (which is actually the default anyway.)

<!-- -->

    recognition.grammars = speechRecognitionList;
    recognition.continuous = false;
    recognition.lang = 'en-US';
    recognition.interimResults = false;
    recognition.maxAlternatives = 1;

#### Starting the speech recognition

After grabbing references to the output [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) and the HTML element (so we can output diagnostic messages and update the app background color later on), we implement an onclick handler so that when the screen is tapped/clicked, the speech recognition service will start. This is achieved by calling [`SpeechRecognition.start()`](../speechrecognition/start). The `forEach()` method is used to output colored indicators showing what colors to try saying.

    var diagnostic = document.querySelector('.output');
    var bg = document.querySelector('html');
    var hints = document.querySelector('.hints');

    var colorHTML= '';
    colors.forEach(function(v, i, a){
      console.log(v, i);
      colorHTML += '<span style="background-color:' + v + ';"> ' + v + ' </span>';
    });
    hints.innerHTML = 'Tap/click then say a color to change the background color of the app. Try ' + colorHTML + '.';

    document.body.onclick = function() {
      recognition.start();
      console.log('Ready to receive a color command.');
    }

#### Receiving and handling results

Once the speech recognition is started, there are many event handlers that can be used to retrieve results, and other pieces of surrounding information (see the [`SpeechRecognition` event handlers list](../speechrecognition#event_handlers).) The most common one you'll probably use is [`SpeechRecognition.onresult`](../speechrecognition/onresult), which is fired once a successful result is received:

    recognition.onresult = function(event) {
      var color = event.results[0][0].transcript;
      diagnostic.textContent = 'Result received: ' + color + '.';
      bg.style.backgroundColor = color;
      console.log('Confidence: ' + event.results[0][0].confidence);
    }

The second line here is a bit complex-looking, so let's explain it step by step. The [`SpeechRecognitionEvent.results`](../speechrecognitionevent/results) property returns a [`SpeechRecognitionResultList`](../speechrecognitionresultlist) object containing [`SpeechRecognitionResult`](../speechrecognitionresult) objects. It has a getter so it can be accessed like an array — so the first `[0]` returns the `SpeechRecognitionResult` at position 0. Each `SpeechRecognitionResult` object contains [`SpeechRecognitionAlternative`](../speechrecognitionalternative) objects that contain individual recognized words. These also have getters so they can be accessed like arrays — the second `[0]` therefore returns the `SpeechRecognitionAlternative` at position 0. We then return its `transcript` property to get a string containing the individual recognized result as a string, set the background color to that color, and report the color recognized as a diagnostic message in the UI.

We also use a [`SpeechRecognition.onspeechend`](../speechrecognition/onspeechend) handler to stop the speech recognition service from running (using [`SpeechRecognition.stop()`](../speechrecognition/stop)) once a single word has been recognized and it has finished being spoken:

    recognition.onspeechend = function() {
      recognition.stop();
    }

#### Handling errors and unrecognized speech

The last two handlers are there to handle cases where speech was recognized that wasn't in the defined grammar, or an error occurred. [`SpeechRecognition.onnomatch`](../speechrecognition/onnomatch) seems to be supposed to handle the first case mentioned, although note that at the moment it doesn't seem to fire correctly; it just returns whatever was recognized anyway:

    recognition.onnomatch = function(event) {
      diagnostic.textContent = 'I didnt recognize that color.';
    }

[`SpeechRecognition.onerror`](../speechrecognition/onerror) handles cases where there is an actual error with the recognition successfully — the [`SpeechRecognitionError.error`](../speechrecognitionerror/error) property contains the actual error returned:

    recognition.onerror = function(event) {
      diagnostic.textContent = 'Error occurred in recognition: ' + event.error;
    }

Speech synthesis
----------------

Speech synthesis (aka text-to-speech, or tts) involves receiving synthesising text contained within an app to speech, and playing it out of a device's speaker or audio output connection.

The Web Speech API has a main controller interface for this — [`SpeechSynthesis`](../speechsynthesis) — plus a number of closely-related interfaces for representing text to be synthesised (known as utterances), voices to be used for the utterance, etc. Again, most OSes have some kind of speech synthesis system, which will be used by the API for this task as available.

### Demo

To show simple usage of Web speech synthesis, we've provided a demo called [Speak easy synthesis](https://mdn.github.io/web-speech-api/speak-easy-synthesis/). This includes a set of form controls for entering text to be synthesised, and setting the pitch, rate, and voice to use when the text is uttered. After you have entered your text, you can press Enter/Return to hear it spoken.

<img src="data:image/png;base64,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" alt="UI of an app called speak easy synthesis. It has an input field in which to input text to be synthesised, slider controls to change the rate and pitch of the speech, and a drop down menu to choose between different voices." width="300" height="533" />

To run the demo, you can clone (or [directly download](https://github.com/mdn/web-speech-api/archive/master.zip)) the Github repo it is part of, open the HTML index file in a supporting desktop browser, or navigate to the [live demo URL](https://mdn.github.io/web-speech-api/speak-easy-synthesis/) in a supporting mobile browser like Chrome, or Firefox OS.

### Browser support

Support for Web Speech API speech synthesis is still getting there across mainstream browsers, and is currently limited to the following:

-   Firefox desktop and mobile support it in Gecko 42+ (Windows)/44+, without prefixes, and it can be turned on by flipping the `media.webspeech.synth.enabled` flag to `true` in `about:config`.

-   Firefox OS 2.5+ supports it, by default, and without the need for any permissions.

-   Chrome for Desktop and Android have supported it since around version 33, without prefixes.

### HTML and CSS

The HTML and CSS are again pretty trivial, containing a title, some instructions for use, and a form with some simple controls. The [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element is initially empty, but is populated with [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option)s via JavaScript (see later on.)

    <h1>Speech synthesiser</h1>

    <p>Enter some text in the input below and press return to hear it. change voices using the dropdown menu.</p>

    <form>
      <input type="text" class="txt">
      <div>
        <label for="rate">Rate</label><input type="range" min="0.5" max="2" value="1" step="0.1" id="rate">
        <div class="rate-value">1</div>
        <div class="clearfix"></div>
      </div>
      <div>
        <label for="pitch">Pitch</label><input type="range" min="0" max="2" value="1" step="0.1" id="pitch">
        <div class="pitch-value">1</div>
        <div class="clearfix"></div>
      </div>
      <select>

      </select>
    </form>

### JavaScript

Let's investigate the JavaScript that powers this app.

#### Setting variables

First of all, we capture references to all the DOM elements involved in the UI, but more interestingly, we capture a reference to [`Window.speechSynthesis`](../window/speechsynthesis). This is API's entry point — it returns an instance of [`SpeechSynthesis`](../speechsynthesis), the controller interface for web speech synthesis.

    var synth = window.speechSynthesis;

    var inputForm = document.querySelector('form');
    var inputTxt = document.querySelector('.txt');
    var voiceSelect = document.querySelector('select');

    var pitch = document.querySelector('#pitch');
    var pitchValue = document.querySelector('.pitch-value');
    var rate = document.querySelector('#rate');
    var rateValue = document.querySelector('.rate-value');

    var voices = [];

#### Populating the select element

To populate the [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select) element with the different voice options the device has available, we've written a `populateVoiceList()` function. We first invoke [`SpeechSynthesis.getVoices()`](../speechsynthesis/getvoices), which returns a list of all the available voices, represented by [`SpeechSynthesisVoice`](../speechsynthesisvoice) objects. We then loop through this list — for each voice we create an [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) element, set its text content to display the name of the voice (grabbed from [`SpeechSynthesisVoice.name`](../speechsynthesisvoice/name)), the language of the voice (grabbed from [`SpeechSynthesisVoice.lang`](../speechsynthesisvoice/lang)), and `-- DEFAULT` if the voice is the default voice for the synthesis engine (checked by seeing if [`SpeechSynthesisVoice.default`](../speechsynthesisvoice/default) returns `true`.)

We also create `data-` attributes for each option, containing the name and language of the associated voice, so we can grab them easily later on, and then append the options as children of the select.

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

When we come to run the function, we do the following. This is because Firefox doesn't support [`SpeechSynthesis.onvoiceschanged`](../speechsynthesis/onvoiceschanged), and will just return a list of voices when [`SpeechSynthesis.getVoices()`](../speechsynthesis/getvoices) is fired. With Chrome however, you have to wait for the event to fire before populating the list, hence the if statement seen below.

    populateVoiceList();
    if (speechSynthesis.onvoiceschanged !== undefined) {
      speechSynthesis.onvoiceschanged = populateVoiceList;
    }

#### Speaking the entered text

Next, we create an event handler to start speaking the text entered into the text field. We are using an [onsubmit](../globaleventhandlers/onsubmit) handler on the form so that the action happens when Enter/Return is pressed. We first create a new [`SpeechSynthesisUtterance()`](../speechsynthesisutterance/speechsynthesisutterance) instance using its constructor — this is passed the text input's value as a parameter.

Next, we need to figure out which voice to use. We use the [`HTMLSelectElement`](../htmlselectelement) `selectedOptions` property to return the currently selected [`<option>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/option) element. We then use this element's `data-name` attribute, finding the [`SpeechSynthesisVoice`](../speechsynthesisvoice) object whose name matches this attribute's value. We set the matching voice object to be the value of the [`SpeechSynthesisUtterance.voice`](../speechsynthesisutterance/voice) property.

Finally, we set the [`SpeechSynthesisUtterance.pitch`](../speechsynthesisutterance/pitch) and [`SpeechSynthesisUtterance.rate`](../speechsynthesisutterance/rate) to the values of the relevant range form elements. Then, with all necessary preparations made, we start the utterance being spoken by invoking [`SpeechSynthesis.speak()`](../speechsynthesis/speak), passing it the [`SpeechSynthesisUtterance`](../speechsynthesisutterance) instance as a parameter.

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

In the final part of the handler, we include an [`SpeechSynthesisUtterance.onpause`](../speechsynthesisutterance/onpause) handler to demonstrate how [`SpeechSynthesisEvent`](../speechsynthesisevent) can be put to good use. When [`SpeechSynthesis.pause()`](../speechsynthesis/pause) is invoked, this returns a message reporting the character number and name that the speech was paused at.

       utterThis.onpause = function(event) {
        var char = event.utterance.text.charAt(event.charIndex);
        console.log('Speech paused at character ' + event.charIndex + ' of "' +
        event.utterance.text + '", which is "' + char + '".');
      }

Finally, we call [blur()](../htmlorforeignelement/blur) on the text input. This is mainly to hide the keyboard on Firefox OS.

      inputTxt.blur();
    }

#### Updating the displayed pitch and rate values

The last part of the code updates the `pitch`/`rate` values displayed in the UI, each time the slider positions are moved.

    pitch.onchange = function() {
      pitchValue.textContent = pitch.value;
    }

    rate.onchange = function() {
      rateValue.textContent = rate.value;
    }

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API/Using_the_Web_Speech_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API/Using_the_Web_Speech_API</a>
