Web Speech API
==============

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The Web Speech API enables you to incorporate voice data into web apps. The Web Speech API has two parts: SpeechSynthesis (Text-to-Speech), and SpeechRecognition (Asynchronous Speech Recognition.)

Web Speech Concepts and Usage
-----------------------------

The Web Speech API makes web apps able to handle voice data. There are two components to this API:

-   Speech recognition is accessed via the [`SpeechRecognition`](speechrecognition) interface, which provides the ability to recognize voice context from an audio input (normally via the device's default speech recognition service) and respond appropriately. Generally you'll use the interface's constructor to create a new [`SpeechRecognition`](speechrecognition) object, which has a number of event handlers available for detecting when speech is input through the device's microphone. The [`SpeechGrammar`](speechgrammar) interface represents a container for a particular set of grammar that your app should recognize. Grammar is defined using [JSpeech Grammar Format](https://www.w3.org/TR/jsgf/) (**JSGF**.)
-   Speech synthesis is accessed via the [`SpeechSynthesis`](speechsynthesis) interface, a text-to-speech component that allows programs to read out their text content (normally via the device's default speech synthesiser.) Different voice types are represented by [`SpeechSynthesisVoice`](speechsynthesisvoice) objects, and different parts of text that you want to be spoken are represented by [`SpeechSynthesisUtterance`](speechsynthesisutterance) objects. You can get these spoken by passing them to the [`SpeechSynthesis.speak()`](speechsynthesis/speak) method.

For more details on using these features, see [Using the Web Speech API](web_speech_api/using_the_web_speech_api).

Web Speech API Interfaces
-------------------------

### Speech recognition

[`SpeechRecognition`](speechrecognition)  
The controller interface for the recognition service; this also handles the [`SpeechRecognitionEvent`](speechrecognitionevent) sent from the recognition service.

[`SpeechRecognitionAlternative`](speechrecognitionalternative)  
Represents a single word that has been recognized by the speech recognition service.

[`SpeechRecognitionError`](speechrecognitionerror)  
Represents error messages from the recognition service.

[`SpeechRecognitionEvent`](speechrecognitionevent)  
The event object for the `result` and `nomatch` events, and contains all the data associated with an interim or final speech recognition result.

[`SpeechGrammar`](speechgrammar)  
The words or patterns of words that we want the recognition service to recognize.

[`SpeechGrammarList`](speechgrammarlist)  
Represents a list of [`SpeechGrammar`](speechgrammar) objects.

[`SpeechRecognitionResult`](speechrecognitionresult)  
Represents a single recognition match, which may contain multiple [`SpeechRecognitionAlternative`](speechrecognitionalternative) objects.

[`SpeechRecognitionResultList`](speechrecognitionresultlist)  
Represents a list of [`SpeechRecognitionResult`](speechrecognitionresult) objects, or a single one if results are being captured in [`continuous`](speechrecognition/continuous) mode.

### Speech synthesis

[`SpeechSynthesis`](speechsynthesis)  
The controller interface for the speech service; this can be used to retrieve information about the synthesis voices available on the device, start and pause speech, and other commands besides.

[`SpeechSynthesisErrorEvent`](speechsynthesiserrorevent)  
Contains information about any errors that occur while processing [`SpeechSynthesisUtterance`](speechsynthesisutterance) objects in the speech service.

[`SpeechSynthesisEvent`](speechsynthesisevent)  
Contains information about the current state of [`SpeechSynthesisUtterance`](speechsynthesisutterance) objects that have been processed in the speech service.

[`SpeechSynthesisUtterance`](speechsynthesisutterance)  
Represents a speech request. It contains the content the speech service should read and information about how to read it (e.g. language, pitch and volume.)

[`SpeechSynthesisVoice`](speechsynthesisvoice)  
Represents a voice that the system supports. Every `SpeechSynthesisVoice` has its own relative speech service including information about language, name and URI.

[`Window.speechSynthesis`](window/speechsynthesis)  
Specced out as part of a `[NoInterfaceObject]` interface called `SpeechSynthesisGetter`, and Implemented by the `Window` object, the `speechSynthesis` property provides access to the [`SpeechSynthesis`](speechsynthesis) controller, and therefore the entry point to speech synthesis functionality.

Examples
--------

The [Web Speech API repo](https://github.com/mdn/web-speech-api/) on GitHub contains demos to illustrate speech recognition and synthesis.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/">Web Speech API</a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`Web_Speech_API`

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

`Web_Speech_API`

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

BCD tables only load in the browser

### SpeechSynthesis

BCD tables only load in the browser

See also
--------

-   [Using the Web Speech API](web_speech_api/using_the_web_speech_api)
-   [SitePoint article](https://www.sitepoint.com/talking-web-pages-and-the-speech-synthesis-api/)
-   [HTML5Rocks article](http://updates.html5rocks.com/2014/01/Web-apps-that-talk---Introduction-to-the-Speech-Synthesis-API)
-   [Demo](https://aurelio.audero.it/demo/speech-synthesis-api-demo.html) \[aurelio.audero.it\]

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API</a>
