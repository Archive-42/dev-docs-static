SpeechRecognitionError
======================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `SpeechRecognitionError` interface of the [Web Speech API](web_speech_api) represents error messages from the recognition service.

This `SpeechRecognitionError` interface was renamed to [`SpeechRecognitionErrorEvent`](speechrecognitionerrorevent) in the Web Speech API specification.

Properties
----------

*`SpeechRecognitionError` also inherits properties from its parent interface, [`Event`](event).*

 [`SpeechRecognitionError.error`](speechrecognitionerror/error) <span class="badge inline readonly">Read only </span>   
Returns the type of error raised.

 [`SpeechRecognitionError.message`](speechrecognitionerror/message) <span class="badge inline readonly">Read only </span>   
Returns a message describing the error in more detail.

Examples
--------

    var recognition = new SpeechRecognition();

    recognition.onerror = function(event) {
      console.log('Speech recognition error detected: ' + event.error);
      console.log('Additional information: ' + event.message);
    }

Browser compatibility
---------------------

No compatibility data found for `api.SpeechRecognitionError`.  
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

-   [Web Speech API](web_speech_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionError" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognitionError</a>
