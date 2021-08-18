SpeechGrammar.SpeechGrammar()
=============================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `SpeechGrammar` constructor of the [`SpeechGrammar`](../speechgrammar) interface creates a new `SpeechGrammar` object instance.

Syntax
------

    var mySpeechGrammar = new SpeechGrammar();

### Parameters

None.

Examples
--------

    var grammar = '#JSGF V1.0; grammar colors; public <color> = aqua | azure | beige | bisque | black | blue | brown | chocolate | coral | crimson | cyan | fuchsia | ghostwhite | gold | goldenrod | gray | green | indigo | ivory | khaki | lavender | lime | linen | magenta | maroon | moccasin | navy | olive | orange | orchid | peru | pink | plum | purple | red | salmon | sienna | silver | snow | tan | teal | thistle | tomato | turquoise | violet | white | yellow ;'
    var recognition = new SpeechRecognition();
    var speechRecognitionList = new SpeechGrammarList();
    speechRecognitionList.addFromString(grammar, 1);
    recognition.grammars = speechRecognitionList;

    var newGrammar = new SpeechGrammar();
    newGrammar.src = '#JSGF V1.0; grammar names; public <name> = chris | kirsty | mike;'
    speechRecognitionList[1] = newGrammar; // should add the new SpeechGrammar object to the list

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/dom-speechgrammar-speechgrammar">Web Speech API<br />
<span class="small">The definition of 'SpeechGrammar()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

See also
--------

-   [Web Speech API](../web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechGrammar/SpeechGrammar" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechGrammar/SpeechGrammar</a>
