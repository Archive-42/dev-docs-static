SpeechGrammarList.addFromString()
=================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `addFromString()` method of the [`SpeechGrammarList`](../speechgrammarlist) interface takes a grammar present in a specific [`DOMString`](../domstring) within the code base (e.g. stored in a variable) and adds it to the `SpeechGrammarList` as a new [`SpeechGrammar`](../speechgrammar) object.

Syntax
------

    speechGrammarListInstance.addFromString(string,weight);

### Returns

Void.

### Parameters

string  
A [`DOMString`](../domstring) representing the grammar to be added.

weight <span class="badge inline optional">Optional</span>   
A float representing the weight of the grammar relative to other grammars present in the [`SpeechGrammarList`](../speechgrammarlist). The weight means the importance of this grammar, or the likelihood that it will be recognized by the speech recognition service. The value can be between `0.0` and `1.0`; If not specified, the default used is `1.0`.

Examples
--------

    var grammar = '#JSGF V1.0; grammar colors; public <color> = aqua | azure | beige | bisque | black | blue | brown | chocolate | coral | crimson | cyan | fuchsia | ghostwhite | gold | goldenrod | gray | green | indigo | ivory | khaki | lavender | lime | linen | magenta | maroon | moccasin | navy | olive | orange | orchid | peru | pink | plum | purple | red | salmon | sienna | silver | snow | tan | teal | thistle | tomato | turquoise | violet | white | yellow ;'
    var recognition = new SpeechRecognition();
    var speechRecognitionList = new SpeechGrammarList();
    speechRecognitionList.addFromString(grammar, 1);
    recognition.grammars = speechRecognitionList;

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechgrammarlist-addfromstring">Web Speech API<br />
<span class="small">The definition of 'addFromString()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`addFromString`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechGrammarList/addFromString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechGrammarList/addFromString</a>
