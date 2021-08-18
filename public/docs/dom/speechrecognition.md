SpeechRecognition
=================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `SpeechRecognition` interface of the [Web Speech API](web_speech_api) is the controller interface for the recognition service; this also handles the [`SpeechRecognitionEvent`](speechrecognitionevent) sent from the recognition service.

**Note**: On some browsers, like Chrome, using Speech Recognition on a web page involves a server-based recognition engine. Your audio is sent to a web service for recognition processing, so it won't work offline.

Constructor
-----------

[`SpeechRecognition.SpeechRecognition()`](speechrecognition/speechrecognition)  
Creates a new `SpeechRecognition` object.

Properties
----------

*`SpeechRecognition` also inherits properties from its parent interface, [`EventTarget`](eventtarget).*

[`SpeechRecognition.grammars`](speechrecognition/grammars)  
Returns and sets a collection of [`SpeechGrammar`](speechgrammar) objects that represent the grammars that will be understood by the current `SpeechRecognition`.

[`SpeechRecognition.lang`](speechrecognition/lang)  
Returns and sets the language of the current `SpeechRecognition`. If not specified, this defaults to the HTML [`lang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html#attr-lang) attribute value, or the user agent's language setting if that isn't set either.

[`SpeechRecognition.continuous`](speechrecognition/continuous)  
Controls whether continuous results are returned for each recognition, or only a single result. Defaults to single (`false`.)

[`SpeechRecognition.interimResults`](speechrecognition/interimresults)  
Controls whether interim results should be returned (`true`) or not (`false`.) Interim results are results that are not yet final (e.g. the [`SpeechRecognitionResult.isFinal`](speechrecognitionresult/isfinal) property is `false`.)

[`SpeechRecognition.maxAlternatives`](speechrecognition/maxalternatives)  
Sets the maximum number of [`SpeechRecognitionAlternative`](speechrecognitionalternative)s provided per result. The default value is 1.

 [`SpeechRecognition.serviceURI`](speechrecognition/serviceuri) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Specifies the location of the speech recognition service used by the current `SpeechRecognition` to handle the actual recognition. The default is the user agent's default speech service.

Methods
-------

*`SpeechRecognition` also inherits methods from its parent interface, [`EventTarget`](eventtarget).*

[`SpeechRecognition.abort()`](speechrecognition/abort)  
Stops the speech recognition service from listening to incoming audio, and doesn't attempt to return a [`SpeechRecognitionResult`](speechrecognitionresult).

[`SpeechRecognition.start()`](speechrecognition/start)  
Starts the speech recognition service listening to incoming audio with intent to recognize grammars associated with the current `SpeechRecognition`.

[`SpeechRecognition.stop()`](speechrecognition/stop)  
Stops the speech recognition service from listening to incoming audio, and attempts to return a [`SpeechRecognitionResult`](speechrecognitionresult) using the audio captured so far.

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`audiostart`](speechrecognition/audiostart_event)  
Fired when the user agent has started to capture audio.  
Also available via the `onaudiostart` property.

[`audioend`](speechrecognition/audioend_event)  
Fired when the user agent has finished capturing audio.  
Also available via the `onaudioend` property.

`end`  
Fired when the speech recognition service has disconnected.  
Also available via the `onend` property.

`error`  
Fired when a speech recognition error occurs.  
Also available via the `onerror` property.

`nomatch`  
Fired when the speech recognition service returns a final result with no significant recognition. This may involve some degree of recognition, which doesn't meet or exceed the [`confidence`](speechrecognitionalternative/confidence) threshold.  
Also available via the `onnomatch` property.

`result`  
Fired when the speech recognition service returns a result — a word or phrase has been positively recognized and this has been communicated back to the app.  
Also available via the `onresult` property.

`soundstart`  
Fired when any sound — recognisable speech or not — has been detected.  
Also available via the `onsoundstart` property.

`soundend`  
Fired when any sound — recognisable speech or not — has stopped being detected.  
Also available via the `onsoundend` property.

`speechstart`  
Fired when sound that is recognized by the speech recognition service as speech has been detected.  
Also available via the `onspeechstart` property.

`speechend`  
Fired when speech recognized by the speech recognition service has stopped being detected.  
Also available via the `onspeechend` property.

`start`  
Fired when the speech recognition service has begun listening to incoming audio with intent to recognize grammars associated with the current `SpeechRecognition`.  
Also available via the `onstart` property.

Examples
--------

In our simple [Speech color changer](https://github.com/mdn/web-speech-api/tree/master/speech-color-changer) example, we create a new `SpeechRecognition` object instance using the [`SpeechRecognition()`](speechrecognition/speechrecognition) constructor, create a new [`SpeechGrammarList`](speechgrammarlist), and set it to be the grammar that will be recognized by the `SpeechRecognition` instance using the [`SpeechRecognition.grammars`](speechrecognition/grammars) property.

After some other values have been defined, we then set it so that the recognition service starts when a click event occurs (see [`SpeechRecognition.start()`](speechrecognition/start).) When a result has been successfully recognized, the [`SpeechRecognition.onresult`](speechrecognition/onresult) handler fires, we extract the color that was spoken from the event object, and then set the background color of the [`<html>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html) element to that color.

    var grammar = '#JSGF V1.0; grammar colors; public <color> = aqua | azure | beige | bisque | black | blue | brown | chocolate | coral | crimson | cyan | fuchsia | ghostwhite | gold | goldenrod | gray | green | indigo | ivory | khaki | lavender | lime | linen | magenta | maroon | moccasin | navy | olive | orange | orchid | peru | pink | plum | purple | red | salmon | sienna | silver | snow | tan | teal | thistle | tomato | turquoise | violet | white | yellow ;'
    var recognition = new SpeechRecognition();
    var speechRecognitionList = new SpeechGrammarList();
    speechRecognitionList.addFromString(grammar, 1);
    recognition.grammars = speechRecognitionList;
    recognition.continuous = false;
    recognition.lang = 'en-US';
    recognition.interimResults = false;
    recognition.maxAlternatives = 1;

    var diagnostic = document.querySelector('.output');
    var bg = document.querySelector('html');

    document.body.onclick = function() {
      recognition.start();
      console.log('Ready to receive a color command.');
    }

    recognition.onresult = function(event) {
      var color = event.results[0][0].transcript;
      diagnostic.textContent = 'Result received: ' + color;
      bg.style.backgroundColor = color;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#speechreco-section">Web Speech API<br />
<span class="small">The definition of 'SpeechRecognition' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`SpeechRecognition`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

4.4.3

You'll need to serve your code through a web server for recognition to work.

33

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

2.0

You'll need to serve your code through a web server for recognition to work.

`SpeechRecognition`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

37

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`abort`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`audioend_event`

33

79

No

No

No

14.1

Yes

Yes

No

No

14.5

Yes

`audiostart_event`

33

79

No

No

No

14.1

Yes

Yes

No

No

14.5

Yes

`continuous`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`end_event`

33

79

No

No

No

14.1

Yes

Yes

No

No

14.5

Yes

`error_event`

33

79

No

No

No

14.1

Yes

Yes

No

No

14.5

Yes

`grammars`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

No

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

No

Yes

You'll need to serve your code through a web server for recognition to work.

`interimResults`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`lang`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`maxAlternatives`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`nomatch_event`

33

79

No

No

No

14.1

Yes

Yes

No

No

14.5

Yes

`onaudioend`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`onaudiostart`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`onend`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`onerror`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`onnomatch`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`onresult`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`onsoundend`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`onsoundstart`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`onspeechend`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`onspeechstart`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`onstart`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`result_event`

33

79

No

No

No

14.1

Yes

Yes

No

No

14.5

Yes

`serviceURI`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

No

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

No

Yes

You'll need to serve your code through a web server for recognition to work.

`soundend_event`

33

79

No

No

No

14.1

Yes

Yes

No

No

14.5

Yes

`soundstart_event`

33

79

No

No

No

14.1

Yes

Yes

No

No

14.5

Yes

`speechend_event`

33

79

No

No

No

14.1

Yes

Yes

No

No

14.5

Yes

`speechstart_event`

33

79

No

No

No

14.1

Yes

Yes

No

No

14.5

Yes

`start`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`start_event`

33

79

No

No

No

14.1

Yes

Yes

No

No

14.5

Yes

`stop`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

Yes

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

See also
--------

-   [Web Speech API](web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition</a>
