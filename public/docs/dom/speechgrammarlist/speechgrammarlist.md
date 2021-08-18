SpeechGrammarList.SpeechGrammarList()
=====================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `SpeechGrammarList()` constructor creates a new `SpeechGrammarList` object instance.

Syntax
------

    var myGrammarList = new SpeechGrammarList();

### Parameters

None.

Examples
--------

In our simple [Speech color changer](https://github.com/mdn/web-speech-api/tree/master/speech-color-changer) example, we create a new `SpeechRecognition` object instance using the [`SpeechRecognition()`](../speechrecognition/speechrecognition) constructor, create a new [`SpeechGrammarList`](../speechgrammarlist), add our grammar string to it using the [`SpeechGrammarList.addFromString`](addfromstring) method, and set it to be the grammar that will be recognized by the `SpeechRecognition` instance using the [`SpeechRecognition.grammars`](../speechrecognition/grammars) property.

    var grammar = '#JSGF V1.0; grammar colors; public <color> = aqua | azure | beige | bisque | black | blue | brown | chocolate | coral | crimson | cyan | fuchsia | ghostwhite | gold | goldenrod | gray | green | indigo | ivory | khaki | lavender | lime | linen | magenta | maroon | moccasin | navy | olive | orange | orchid | peru | pink | plum | purple | red | salmon | sienna | silver | snow | tan | teal | thistle | tomato | turquoise | violet | white | yellow ;'
    var recognition = new SpeechRecognition();
    var speechRecognitionList = new SpeechGrammarList();
    speechRecognitionList.addFromString(grammar, 1);
    recognition.grammars = speechRecognitionList;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#speechreco-speechgrammarlist">Web Speech API<br />
<span class="small">The definition of 'SpeechGrammarList' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`SpeechGrammarList`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechGrammarList/SpeechGrammarList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechGrammarList/SpeechGrammarList</a>
