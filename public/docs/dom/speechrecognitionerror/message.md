SpeechRecognitionError.message
==============================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `message` read-only property of the [`SpeechRecognitionError`](../speechrecognitionerror) interface returns a message describing the error in more detail.

This `SpeechRecognitionError` interface was renamed to [`SpeechRecognitionErrorEvent`](../speechrecognitionerrorevent) in the Web Speech API specification.

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

Browser compatibility
---------------------

No compatibility data found for `api.SpeechRecognitionError.message`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionError/message" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionError/message</a>
