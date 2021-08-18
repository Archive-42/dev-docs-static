SpeechRecognitionErrorEvent.message
===================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `message` read-only property of the [`SpeechRecognitionErrorEvent`](../speechrecognitionerrorevent) interface returns a message describing the error in more detail.

Syntax
------

    var myErrorMsg = event.message;

### Value

A [`DOMString`](../domstring) containing more details about the error that was raised. Note that the spec does not define the exact wording of these messages — this is up to the implementors to decide upon.

Examples
--------

    var recognition = new SpeechRecognition();

    recognition.onerror = function(event) {
      console.log('Speech recognition error detected: ' + event.error);
      console.log('Additional information: ' + event.message);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/speech-api/#dom-speechrecognitionerrorevent-message">Web Speech API<br />
<span class="small">The definition of 'message' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

-   [Web Speech API](../web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionErrorEvent/message" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionErrorEvent/message</a>
