SpeechGrammar
=============

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `SpeechGrammar` interface of the [Web Speech API](web_speech_api) represents a set of words or patterns of words that we want the recognition service to recognize.

Grammar is defined using [JSpeech Grammar Format](https://www.w3.org/TR/jsgf/) (**JSGF**.) Other formats may also be supported in the future.

Constructor
-----------

 [`SpeechGrammar.SpeechGrammar()`](speechgrammar/speechgrammar) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Creates a new `SpeechGrammar` object.

Properties
----------

[`SpeechGrammar.src`](speechgrammar/src)  
Sets and returns a string containing the grammar from within in the `SpeechGrammar` object instance.

 [`SpeechGrammar.weight`](speechgrammar/weight) <span class="badge inline optional">Optional</span>   
Sets and returns the weight of the `SpeechGrammar` object.

Examples
--------

    var grammar = '#JSGF V1.0; grammar colors; public <color> = aqua | azure | beige | bisque | black | blue | brown | chocolate | coral | crimson | cyan | fuchsia | ghostwhite | gold | goldenrod | gray | green | indigo | ivory | khaki | lavender | lime | linen | magenta | maroon | moccasin | navy | olive | orange | orchid | peru | pink | plum | purple | red | salmon | sienna | silver | snow | tan | teal | thistle | tomato | turquoise | violet | white | yellow ;'
    var recognition = new SpeechRecognition();
    var speechRecognitionList = new SpeechGrammarList();
    speechRecognitionList.addFromString(grammar, 1);
    recognition.grammars = speechRecognitionList;

    console.log(speechRecognitionList[0].src); // should return the same as the contents of the grammar variable
    console.log(speechRecognitionList[0].weight); // should return 1 - the same as the weight set in line 4.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#speechreco-speechgrammar">Web Speech API<br />
<span class="small">The definition of 'SpeechGrammar' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`SpeechGrammar`

25

79

44

Note that currently only the speech synthesis part is available in Firefox Desktop - the speech recognition part will be available soon, once the required internal permissions are sorted out.

No

27

No

No

64

No

No

No

9.0

`SpeechGrammar`

25

79

44

Note that currently only the speech synthesis part is available in Firefox Desktop - the speech recognition part will be available soon, once the required internal permissions are sorted out.

No

27

No

No

64

No

No

No

9.0

`src`

25

79

44

Note that currently only the speech synthesis part is available in Firefox Desktop - the speech recognition part will be available soon, once the required internal permissions are sorted out.

No

27

No

No

64

No

No

No

9.0

`weight`

25

79

44

Note that currently only the speech synthesis part is available in Firefox Desktop - the speech recognition part will be available soon, once the required internal permissions are sorted out.

No

27

No

No

64

No

No

No

9.0

See also
--------

-   [Web Speech API](web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechGrammar" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechGrammar</a>
