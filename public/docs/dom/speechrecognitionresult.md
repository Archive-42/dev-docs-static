SpeechRecognitionResult
=======================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `SpeechRecognitionResult` interface of the [Web Speech API](web_speech_api) represents a single recognition match, which may contain multiple [`SpeechRecognitionAlternative`](speechrecognitionalternative) objects.

Properties
----------

 [`SpeechRecognitionResult.isFinal`](speechrecognitionresult/isfinal) <span class="badge inline readonly">Read only </span>   
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that states whether this result is final (true) or not (false) — if so, then this is the final time this result will be returned; if not, then this result is an interim result, and may be updated later on.

 [`SpeechRecognitionResult.length`](speechrecognitionresult/length) <span class="badge inline readonly">Read only </span>   
Returns the length of the "array" — the number of [`SpeechRecognitionAlternative`](speechrecognitionalternative) objects contained in the result (also referred to as "n-best alternatives".)

Methods
-------

[`SpeechRecognitionResult.item`](speechrecognitionresult/item)  
A standard getter that allows [`SpeechRecognitionAlternative`](speechrecognitionalternative) objects within the result to be accessed via array syntax.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#speechreco-result">Web Speech API<br />
<span class="small">The definition of 'SpeechRecognitionResult' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`SpeechRecognitionResult`

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

`isFinal`

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

`item`

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

`length`

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

-   [Web Speech API](web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionResult" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionResult</a>
