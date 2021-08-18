SpeechRecognitionAlternative.transcript
=======================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `transcript` read-only property of the [`SpeechRecognitionResult`](../speechrecognitionresult) interface returns a string containing the transcript of the recognized word(s).

For continuous recognition, leading or trailing whitespace will be included where necessary so that concatenation of consecutive [`SpeechRecognitionResult`](../speechrecognitionresult)s produces a proper transcript of the session.

Syntax
------

    var myTranscript = speechRecognitionAlternativeInstance.transcript;

### Returns

A [`DOMString`](../domstring).

Examples
--------

This code is excerpted from our [Speech color changer](https://github.com/mdn/web-speech-api/blob/master/speech-color-changer/script.js) example.

    recognition.onresult = function(event) {
      // The SpeechRecognitionEvent results property returns a SpeechRecognitionResultList object
      // The SpeechRecognitionResultList object contains SpeechRecognitionResult objects.
      // It has a getter so it can be accessed like an array
      // The first [0] returns the SpeechRecognitionResult at position 0.
      // Each SpeechRecognitionResult object contains SpeechRecognitionAlternative objects that contain individual results.
      // These also have getters so they can be accessed like arrays.
      // The second [0] returns the SpeechRecognitionAlternative at position 0.
      // We then return the transcript property of the SpeechRecognitionAlternative object
      var color = event.results[0][0].transcript;
      diagnostic.textContent = 'Result received: ' + color + '.';
      bg.style.backgroundColor = color;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechrecognitionalternative-transcript">Web Speech API<br />
<span class="small">The definition of 'transcript' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`transcript`

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

-   \[1\] Speech recognition interfaces are currently prefixed on Chrome, so you'll need to prefix interface names appropriately, e.g. `webkitSpeechRecognition`; You'll also need to serve your code through a web server for recognition to work.
-   \[2\] Can be enabled via the `media.webspeech.recognition.enable` flag in about:config, although note that currently speech recognition won't work on Desktop Firefox — it will be properly exposed soon, once the required internal permissions are sorted out.

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionAlternative/transcript" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionAlternative/transcript</a>
