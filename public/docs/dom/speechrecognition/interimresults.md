SpeechRecognition.interimResults
================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `interimResults` property of the [`SpeechRecognition`](../speechrecognition) interface controls whether interim results should be returned (`true`) or not (`false`.) Interim results are results that are not yet final (e.g. the [`SpeechRecognitionResult.isFinal`](../speechrecognitionresult/isfinal) property is `false`.)

The default value for `interimResults` is `false`.

Syntax
------

    var myInterimResult = mySpeechRecognition.interimResults;
    mySpeechRecognition.interimResults = false;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) representing the state of the current `SpeechRecognition`'s interim results. `true` means interim results are returned, and `false` means they aren't.

Examples
--------

This code is excerpted from our [Speech color changer](https://github.com/mdn/web-speech-api/blob/master/speech-color-changer/script.js) example.

    var grammar = '#JSGF V1.0; grammar colors; public <color> = aqua | azure | beige | bisque | black | blue | brown | chocolate | coral | crimson | cyan | fuchsia | ghostwhite | gold | goldenrod | gray | green | indigo | ivory | khaki | lavender | lime | linen | magenta | maroon | moccasin | navy | olive | orange | orchid | peru | pink | plum | purple | red | salmon | sienna | silver | snow | tan | teal | thistle | tomato | turquoise | violet | white | yellow ;'
    var recognition = new SpeechRecognition();
    var speechRecognitionList = new SpeechGrammarList();
    speechRecognitionList.addFromString(grammar, 1);
    recognition.grammars = speechRecognitionList;
    //recognition.continuous = false;
    recognition.lang = 'en-US';
    recognition.interimResults = false;
    recognition.maxAlternatives = 1;

    ...

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechrecognition-interimresults">Web Speech API<br />
<span class="small">The definition of 'interimResults' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

### Firefox OS permissions

To use speech recognition in an app, you need to specify the following permissions in your [manifest](https://developer.mozilla.org/en-US/docs/Web/Apps/Build/Manifest):

    "permissions": {
      "audio-capture" : {
        "description" : "Audio capture"
      },
      "speech-recognition" : {
        "description" : "Speech recognition"
      }
    }

You also need a privileged app, so you need to include this as well:

      "type": "privileged"

See also
--------

-   [Web Speech API](../web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition/interimResults" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition/interimResults</a>
