SpeechRecognitionEvent
======================

The `SpeechRecognitionEvent` interface of the [Web Speech API](web_speech_api) represents the event object for the `result` and `nomatch` events, and contains all the data associated with an interim or final speech recognition result.

Properties
----------

*`SpeechRecognitionEvent` also inherits properties from its parent interface, [`Event`](event).*

 [`SpeechRecognitionEvent.emma`](speechrecognitionevent/emma) <span class="badge inline readonly">Read only </span>   
Returns an Extensible MultiModal Annotation markup language (EMMA) — XML — representation of the result.

 [`SpeechRecognitionEvent.interpretation`](speechrecognitionevent/interpretation) <span class="badge inline readonly">Read only </span>   
Returns the semantic meaning of what the user said.

 [`SpeechRecognitionEvent.resultIndex`](speechrecognitionevent/resultindex) <span class="badge inline readonly">Read only </span>   
Returns the lowest index value result in the [`SpeechRecognitionResultList`](speechrecognitionresultlist) "array" that has actually changed.

 [`SpeechRecognitionEvent.results`](speechrecognitionevent/results) <span class="badge inline readonly">Read only </span>   
Returns a [`SpeechRecognitionResultList`](speechrecognitionresultlist) object representing all the speech recognition results for the current session.

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#speechreco-event">Web Speech API<br />
<span class="small">The definition of 'SpeechRecognitionEvent' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`SpeechRecognitionEvent`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

≤37

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`emma`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

No

≤37

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

No

Yes

You'll need to serve your code through a web server for recognition to work.

`interpretation`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

No

≤37

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

No

Yes

You'll need to serve your code through a web server for recognition to work.

`resultIndex`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

≤37

You'll need to serve your code through a web server for recognition to work.

Yes

You'll need to serve your code through a web server for recognition to work.

No

No

14.5

Yes

You'll need to serve your code through a web server for recognition to work.

`results`

33

You'll need to serve your code through a web server for recognition to work.

≤79

You'll need to serve your code through a web server for recognition to work.

No

No

No

14.1

≤37

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionEvent</a>
