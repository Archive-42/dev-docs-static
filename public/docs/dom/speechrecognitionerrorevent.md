SpeechRecognitionErrorEvent
===========================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `SpeechRecognitionErrorEvent` interface of the [Web Speech API](web_speech_api) represents error messages from the recognition service.

Properties
----------

*`SpeechRecognitionErrorEvent` also inherits properties from its parent interface, [`Event`](event).*

 [`SpeechRecognitionErrorEvent.error`](speechrecognitionerrorevent/error) <span class="badge inline readonly">Read only </span>   
Returns the type of error raised.

 [`SpeechRecognitionErrorEvent.message`](speechrecognitionerrorevent/message) <span class="badge inline readonly">Read only </span>   
Returns a message describing the error in more detail.

Examples
--------

    var recognition = new SpeechRecognition();

    recognition.onerror = function(event) {
      console.log('Speech recognition error detected: ' + event.error);
      console.log('Additional information: ' + event.message);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#speechrecognitionerrorevent">Web Speech API<br />
<span class="small">The definition of 'SpeechRecognitionErrorEvent' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`SpeechRecognitionErrorEvent`

77

You'll need to serve your code through a web server for recognition to work.

33-77

79

No

No

No

14.1

77

You'll need to serve your code through a web server for recognition to work.

≤37-77

77

You'll need to serve your code through a web server for recognition to work.

33-77

No

No

14.5

12.0

You'll need to serve your code through a web server for recognition to work.

2.0-12.0

`error`

77

79

No

No

No

14.1

77

77

No

No

14.5

12.0

`message`

77

79

No

No

No

14.1

77

77

No

No

14.5

12.0

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionErrorEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionErrorEvent</a>
